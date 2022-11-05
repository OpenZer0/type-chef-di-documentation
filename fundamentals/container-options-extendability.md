# 🍎 Container Options, extendability

You can configure the Container with

```typescript
{
    enableAutoCreate: boolean; // if dependency does not exist in the container, create it and register
    initializers?: Type<IInitializer>[]; // runs after instatnitation 
}
```

### enableAutoCreate

When you call container.resolve / resolveByType etc. It will try to resolve with the registered dependencies and if the required dependency is not registered (.register, .registerByType..)  it will throw an error, BUT you have the option to register types when resolution is happening (no need for registration). It will resolve Types automatically with the use of the [injectable.md](decorators/injectable.md "mention") decorator. Basically, it's like a strict mode you can choose.

### Initializers

Initializers run after every instantiation. The container has some default initializatizers eg. @Init, @InjectProperty, @RunBefore. You can create your own just implement the IInitializer interface:

```typescript
class StatusInitializer implements IInitializer {
    constructor(readonly resolver: IResolver) {
    }

    run(resolvedInstance: any, definition: IBaseDefinition): Promise<any> {
        resolvedInstance.status = "your change";
        return resolvedInstance;
    }
}
```

Then add to the container:

```typescript
new Container({
    initializers: [StatusInitializer]
})
```
