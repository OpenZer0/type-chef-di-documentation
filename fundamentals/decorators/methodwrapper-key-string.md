# 🌕 @MethodWrapper(key: string | Type\<IMethodWrapper>)





```typescript
    
class Wrapper implements IMethodWrapper {
    constructor() { // DI will resolve dependencies (type & key injection)
    }
    
    run(next: Function, params: any[]) {
        // run code before
        next()
        // run code after
    }
}

```

```typescript
 class Test {

    @MethodWrapper(MyMethodWrapper) // or use registerd string key
    methodWrapper(p1:string, p2: string){
        console.log("original fn: ", p1, p2)
        // ...
    }       
} 

    
```
