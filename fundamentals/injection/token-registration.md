---
description: register, registerTypes, asSingleton, asFactory
---

# 🍪 Token registration

Value can be a class definition, primitive, or a function.

```typescript
container.register('key', value)
```

New Instance

```typescript
container.register('key2', value).asPrototype()
```

Use the same instance (default)

```typescript
container.register('key3', value).asSingleton()
```

Register with context: @Inject('paramKey') ... it will replace injection keys (this enables to create different variants)

```typescript
container.register('key4', value)
    .asSingleton()
    .withContext({'paramKey': 'otherKey', 'paramKey2': 'otherKey2'})
```

Register constant (can be primitive, function, etc)

```typescript
container.register('key4', 'some constant').asConstant()
```

Registration by type with a random key (if you don't want to enable auto-creation you can still use this)

```typescript
container.registerTypes([MyClass, Myclass2])
```

Factory

```typescript
container.register('factoryKey', FactoryClass).asFactory();
container.register('factoryResult', String).asFactoryResult('factoryKey');
```
