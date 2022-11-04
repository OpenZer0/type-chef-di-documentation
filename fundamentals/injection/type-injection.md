# 🍕 Type injection

The simplest way to resolve classes is the Type resolution \*(resolveByType)

To enabale it when you create the container use param {enableAutoCreate: true}

```typescript
const container = new Container({enableAutoCreate: true});
const service = await container.resolveByType<Service>(Service);
```

{% hint style="info" %}
Make sure all the class dependency has the @Injectable decorator
{% endhint %}

```typescript
import { Container, Injectable } from "type-chef-di";

@Injectable
class SayService {

    public getString() {
        return "pizza";
    }
}

@Injectable
class SayService2 {

    public getString() {
        return "coffee";
    }
}


@Injectable
class Client {
    constructor(private readonly sayService: SayService, private readonly sayService2: SayService2) {
    }

    public say() {
        return `I like ${this.sayService.getString()} and ${this.sayService2.getString()}`;
    }
}

@Injectable
class Service {
    constructor(private readonly client: Client) {
    }

    public check() {
        return `client says: ${this.client.say()}`;
    }
}


async function run() {
    const container = new Container({enableAutoCreate: true});
    const service = await container.resolveByType<Service>(Service); // new Service(new Client(new SayService(), new SayService2()));
    console.log(service.check()); // client says: I like pizza and coffee
}

run();
```
