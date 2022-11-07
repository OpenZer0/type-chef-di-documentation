# Table of contents

* [👋 Welcome to type-chef-di documentation](README.md)

## Overview

* [✨ Getting started](overview/getting-started.md)

## Fundamentals

* [🍎 Container Options, extendability](fundamentals/container-options-extendability.md)
* [👨🍳 Injection](fundamentals/injection/README.md)
  * [🍕 Type injection](fundamentals/injection/type-injection.md)
  * [🍪 Token registration](fundamentals/injection/token-registration.md)
  * [☕ Token Injection](fundamentals/injection/token-injection.md)
  * [🌮 Mixed injection](fundamentals/injection/mixed-injection.md)
* [🛠 Decorators](fundamentals/decorators/README.md)
  * [✅ @Injectable({instantiation: "singleton" | "prototype"})](fundamentals/decorators/injectable.md)
  * [🎯 @Inject\<T>(key: string | Type\<T>)](fundamentals/decorators/inject-key-string.md)
  * [🍍 @InjectProperty\<T>(key: string | Type\<T>)](fundamentals/decorators/injectproperty-key-string.md)
  * [🍭 @Setter()](fundamentals/decorators/setter.md)
  * [🔆 @InitMethod()](fundamentals/decorators/initmethod.md)
  * [🏭 @FactoryMethod()](fundamentals/decorators/factorymethod.md)
  * [⚡ @AddTags(tags)](fundamentals/decorators/addtags-tags.md)
  * [🪃 @RunBefore(key: string | Type\<IRunBefore>)](fundamentals/decorators/runbefore-key-string.md)
  * [🛴 @RunAfter(key: string | Type\<IRunAfter>)](fundamentals/decorators/runafter-key-string.md)
  * [🌕 @MethodWrapper(key: string | Type\<IMethodWrapper>)](fundamentals/decorators/methodwrapper-key-string.md)

## Use Cases

* [🎨 Plans](use-cases/plans.md)
* [🖥 For Developers](use-cases/for-developers.md)

## Other

* [💡 DI / IoC](other/di-ioc.md)
