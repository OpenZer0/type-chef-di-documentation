# 🍭 @Setter()

Setter will run after class instantiation. It can use [inject-key-string.md](inject-key-string.md "mention")

```typescript
 const container = new Container();
        class SetterTestClass {
            panda: string = "sad panda";
            @Setter()
            set pandaSetter(@Inject('param1') param1: string) {
                this.panda = param1;
            }
            constructor() {
            }
        }
        const param1 = "happy panda"
        container.register('SetterTestClass', SetterTestClass);
        container.register('param1', param1)
        const setterTestClass = await container.resolve<SetterTestClass>('SetterTestClass');
        console.log(setterTestClass.panda) // it should be "happy panda"
```
