# ⚡ @AddTags(tags)

Tag resolution:

```typescript

@AddTags("tag1")
class Foo1 {
}

@AddTags(["tag2", "tagMultiple"])
class Foo2 {
}

@AddTags(["tag3", "tagMultiple"])
class Foo3 {
}

const container = new Container();
container.registerTypes([Foo1, Foo2, Foo3]);

const res1 = await container.resolveByTags("tagMultiple"); // return [ new Foo2(), new Foo3()]
const res2 = await container.resolveByTags("tagMultiple", "tag1"]); // return [new Foo1(), new Foo2(), new Foo3()]
  
```
