# 🛴 @RunAfter(key: string | Type\<IRunAfter>)



```typescript
 class MyRunAfter implements IRunAfter {
      constructor() { // DI will resolve dependencies (type & key injection)
    }
    
    run() {
        console.log('run this after.')
    }
}

class Test {

    @RunAfter(MyRunAfter)  // or use registerd string key
    after(p1:string, p2: string){
        console.log("original fn: ", p1, p2)
            // ...
    }
        
}
  
}
```
