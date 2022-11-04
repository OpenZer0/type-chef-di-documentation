# Token registration



value can be a class definition, constant or a function

```typescript
container.register('key', value)
```

new instance (default)

```typescript
container.register('key2', value).asPrototype()
```

as singleton (use the same instance)

```typescript
container.register('key3', value).asSingleton()
```

register with context: @Inject('paramKey') ... it will replace to 'otherKey'

```typescript
container.register('key4', value)
    .asSingleton()
    .withContext({'paramKey': 'otherKey', 'paramKey2': 'otherKey2'})
```

register constant

```typescript
container.register('key4', 'some constant').asConstant()
```

registrate by type (if you dont want to enable auto creaton you can still use this)

```typescript
container.registerTypes([MyClass, Myclass2])
```

factory

```typescript
container.register('factoryKey', FactoryClass).asFactory();
container.register('factoryResult', String).asFactoryResult('factoryKey');
```
