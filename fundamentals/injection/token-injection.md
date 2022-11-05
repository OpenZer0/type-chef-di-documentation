# ☕ Token Injection

If you want more control over the injection process you can use the token injection. This lets you inject the value that you registered.

{% hint style="info" %}
The di can't resolve automatically the primitive types, eg. string, number, interfaces... You must specify [token-registration.md](token-registration.md "mention") the value and use the @Inject decorator for that
{% endhint %}

```typescript
class Service {

    constructor(@Inject("serviceStr") private readonly value: string) {
    }

    public say() {
        return `${this.value}`;
    }
}
class Client {

    constructor(@Inject("clientStr") private readonly value: string, @Inject("service") private readonly service: Service) {
    }

    public say() {
        return `I like ${this.value} and ${this.service.say()}`;
    }
}


async function run() {
    const container = new Container();
    container.register("clientStr", "coffee");
    container.register("serviceStr", "pizza");
    container.register("service", Service);
    container.register("client", Client);
    const service = await container.resolve<Client>("client"); // new Service('pizza');
    const service2 = await container.resolveByType<Client>(Client); // new Client('coffee', new Service('pizza'));
    console.log(service.say()); // client says: I like pizza and coffee
    console.log(service2.say()); // client says: I like pizza and coffee
}

run();
```
