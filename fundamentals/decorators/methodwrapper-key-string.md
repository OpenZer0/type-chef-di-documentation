# 🌕 @MethodWrapper(key: string | Type\<IMethodWrapper>)



```typescript

export class MeasureWrapper implements IMethodWrapper {
    constructor() { // DI will resolve dependencies (type & key injection)
    }

    async run(next: Function, params: any[]) {
        // run code before
        const start = new Date().getTime();
        
        // call original fn
        const res = await next() // (params automatically added)
        
        //run code after
        const end = new Date().getTime();
        const time = end - start;
        console.log(`Execution time: ${time} ms`)
        
        // return fn result
        return res;
    }

}

```

```typescript
 class Test {

    @MeasureWrapper(MyMethodWrapper) // or use registerd string key
    methodWrapper(p1:string, p2: string){
        console.log("original fn: ", p1, p2)
        // ...
    }       
} 

    
```
