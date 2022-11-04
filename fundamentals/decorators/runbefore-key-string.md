# 🪃 @RunBefore(key: string)



**!! Currently don't work with "this" ref !!**

* you can use this decorators individually or together



```typescript
 class Test {
        @MethodWrapper('MyMethodWrapper')
        @RunAfter('MyRunAfter')
        @RunBefore('MyRunBefore')
        testFn(p: string, p2: string) {
            console.log("p = " + p, " p2 = " + p2);
        }
    }
    class MyRunAfter implements IRunAfter {
        run(): void {
            console.log('run this after.')
        }
    }
    class MyRunBefore implements IRunBefore {
        run() {
            console.log("run before.")
        }
    }
    class MyMethodWrapper implements IMethodWrapper {
        run(next: Function, params: any[]): any {
            console.log("wrapper before.")
            next(...params);
            console.log("wrapper after.")
        }
    }
}
    container.register('MyRunBefore', MyRunBefore);
    container.register('MyRunAfter', MyRunAfter);
    container.register('MyMethodWrapper', MyMethodWrapper);
    container.register('test', Test);
    const testObj = await container.resolve<Test>('test');
    testObj.testFn('test', 'test2');
// log result:    
/*
wrapper before.
run before.
p = test  p2 = test2
run this after.
wrapper after.
*/
```
