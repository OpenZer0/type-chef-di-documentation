# 🍍 @InjectProperty(key: string)

Basically the same as [inject-key-string.md](inject-key-string.md "mention") but with class properties.

```typescript
class Test {
        @InjectProperty('value')
        testProp: any;
        
        @InjectProperty('value2')
        testProp2: any;
        
        constructor() {
        }
    }
    container.register('value', 'happy');
    container.register('value2', 'panda');
    container.register('test', Test);
    const testObj = await container.resolve<Test>('test');
    console.log(`I am a ${testObj.testProp} ${testObj.testProp2}`) // result: I am a happy panda
```
