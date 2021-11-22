# Bridge Methods Demo

An example which demonstrates how to narrow down the return type of a Java method in a new version of a Java library,
using [Bridger](https://github.com/dmlloyd/bridger) to keep backwards compatibility.

In _service-1.0_, there's a method `Number SomeService::getSomeNumber()`.
In _service-2.0_, this return type is narrowed down to `Long`.
Consequently, the integration test in _integration-test_ fail,
as it uses _client_, as built against _service-1.0_, together with _service-2.0_.
Switch to version 3.0.0 to make the test pass.
This works as _service-3.0_ injects a bridge method which returns `Number`.

## Build

Run the following command to build this project:

```
mvn clean verify
```

## License

This code base is available under the Apache License, version 2.
