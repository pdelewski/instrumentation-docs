## OTEL instrumentation technologies/languages (partial list)

| `Instrumentation`  | `Java (JVM)`                   | `.Net (CLR)`                                    | `Go (Native, machine code`                             | `PHP (Zend engine)`           |
|--------------------|--------------------------------|-------------------------------------------------|--------------------------------------------------------|-------------------------------|
| `Manual`           | `JAVA at compile time`         | `C# (managed language) at compile time`         | `Go at compile time`                                   | `PHP at compile time`         |
| `Automatic`        | `JAVA at runtime`              | `C/C++, C# or other .Net language at runtime`   | `C/C++, Go at runtime or at compile time via autotel`  | `C/C++, PHP at runtime`       |

### java manual instrumentation

```
Span span = tracer.spanBuilder("my span").startSpan();

// Make the span the current span
try (Scope ss = span.makeCurrent()) {
  // In this scope, the span is the current/active span
} finally {
    span.end();
}
```

### .Net manual instrumentation

```
using var myActivity = MyActivitySource.StartActivity("SayHello");
```
