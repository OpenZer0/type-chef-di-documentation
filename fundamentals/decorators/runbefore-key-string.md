# 🪃 @RunBefore(key: string | Type\<IRunBefore>)

****

* you can use this decorators individually or together

```typescript
 
class MyRunBefore implements IRunBefore {
     constructor() { // DI will resolve dependencies (type & key injection)
    }
    
    run() {
        console.log("run before.")
    }
 }

class Test {
  @RunBefore(MyRunBefore)  // or use registered string key
  before(p1:string, p2: string){
    console.log("original fn: ", p1, p2)
    // ...
 }
}
```
