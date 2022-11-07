# 🍍 @InjectProperty\<T>(key: string | Type\<T>)

Basically the same as [inject-key-string.md](inject-key-string.md "mention") but with class properties.

```typescript
interface IFoo {
    getNumber(): number;
}

class Foo implements IFoo {
   getNumber() {
       return 69;
   }
}

class Foo2 implements IFoo {
    getNumber() {
        return 420;
    }
}
        
class Test {
        @InjectProperty('value')
        testProp: any;
        
        @InjectProperty('value2')
        testProp2: any;
        
        
        @InjectProperty<IFoo>(Foo)
        testProp!: IFoo; // 69

        @InjectProperty<IFoo>(Foo2)
        testProp2!: IFoo; //420
        
        constructor() {
        }
    }
    container.register('value', 'happy');
    container.register('value2', 'panda');
    container.register('test', Test);
    const testObj = await container.resolve<Test>('test');
    console.log(`I am a ${testObj.testProp} ${testObj.testProp2}`) // result: I am a happy panda
```
