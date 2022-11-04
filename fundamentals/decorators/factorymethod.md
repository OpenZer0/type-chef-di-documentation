# 🏭 @FactoryMethod()



```typescript
export class FactoryClass {
    constructor(@Inject("factoryParam1") private readonly value: string) {
    }
    getValue() {
        return this.value;
    }
    create() {
        return "This is ths FactoryClass create() result."
    }
    @FactoryMethod()
    factoryMethodName(@Inject('factoryMethodKey1') value: string, @Inject('factoryMethodKey2') value2: string) {
        return "factoryMethodName result: value: " + value + " value2: " + value2;
    }
    create2() {
        return "create2 result";
    }
}
const container = new Container();
const firstFactoryParam = "firstFactoryParam";
const secondFactoryParam = "secondFactoryParam";
container.register('factoryParam1', 'factoryParam1 constant data').asConstant()
container.register('factoryMethodKey1', firstFactoryParam).asConstant();
container.register('factoryMethodKey2', secondFactoryParam).asConstant();
container.register('factoryKey', FactoryClass).asFactory()
// if asFactory() param empty call the @FactoryMethod fn, but if it is not exist default is create()
container.register('factoryResult', String).asFactoryResult('factoryKey');
const factoryResult = container.resolve<String>('factoryResult'); // it will be "factoryResult:  factoryMethodName result: value: firstFactoryParam value2: secondFactoryParam"
container.register('otherParam1', 'replaced1').asConstant();
container.register('otherParam2', 'replaced2').asConstant();
container.register('factoryKey2', FactoryClass).asFactory();
container.register('factoryResult2', String).asFactoryResult('factoryKey2').withMethodContext({'factoryMethodKey1': 'otherParam1', 'factoryMethodKey2': 'otherParam2'});
const factoryResult2 = container.resolve<String>('factoryResult2'); // it will be: factoryResult:  factoryMethodName result: value: replaced1 value2: replaced2
```
