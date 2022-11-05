# ✅ @Injectable({instantiation: "singleton" | "prototype"})

```typescript
@Injectable()
class Something {

    public getValue() {
        return "more";
    }
}

@Injectable()
class SomethingElse {
    constructor(private readonly something: Something, private readonly str: string = "pizza") {
    }

    public getValue() {
        return `need ${this.something.getValue()} ${this.str}`;
    }
}

@Injectable()
class Client {
    constructor(private readonly something: Something, private readonly somethingElse: SomethingElse) {
    }

    public say() {
        return `I ${this.somethingElse.getValue()} and ${this.something.getValue()} coffee.`;
    }
}

@Injectable()
class Service {
    constructor(private readonly client: Client) {
    }

    public check() {
        return `client says: ${this.client.say()}`;
    }
}

// create the container
const container = new Container({enableAutoCreate: true});

// resolve without registration any @Injectable class
const service = await container.resolveByType<Service>(Service);

console.log(service.check());  // it will be: "client says: I need more pizza and more coffee."
```
