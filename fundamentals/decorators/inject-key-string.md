# 🎯 @Inject(key: string)

Inject registered key value to constructor.

```typescript
constructor(service: Service, @Inject('options') options: IOptions)
```

If the key is not registered, the resolution process will fail.

You can check the container after you finished the configuration:

container.done() or container.containerTest()

This will try to resolve all the registered keys, and types.
