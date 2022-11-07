# 🎯 @Inject\<T>(key: string | Type\<T>)

Inject registered key value to constructor.

```typescript
constructor(service: Service,
 @Inject('options') options: IOptions)

constructor(service: Service,
 @Inject<IOptions>(OptionClass) options: IOptions,
 @Inject<IOptions>(OptionClass2) options2: IOptions)
```

Explanation:

* <mark style="color:green;">service: Service</mark>: if {enableAutoCreate: true} you don't have to do anything it will register and resolve automatically. if false you need to register before resolution eg container.registerByType(Service)  but you can inject it with @Inject if you want.
* <mark style="color:green;">@Inject('options') options: IOptions</mark> - this cannot be resolved automatically because this is just a general interface (IOptions), you need to specify (by registering) a token eg 'option' and inject via @Inject("key")
* <mark style="color:green;">@Inject(OptionClass) options: IOptions, @Inject\<IOptions>(OptionClass2) options2: IOptions)</mark> - You can directly specify the class that you want to inject, this way you don't need to register the OptionClass (the generic will check the passed type correctness)

If the key is not registered, the resolution process will fail.

You can check the container after you finished the configuration:

container.done() or container.containerTest()

This will try to resolve all the registered keys, and types.
