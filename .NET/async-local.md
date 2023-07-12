## Keynote

AsyncLocal<T> can persist a TValue across an asynchronous flow. Each time you enter an async method **a fresh new async context is initiated deriving from its parent async context**.

So every time a new async context is created, a shallow copy of the current TValue in the parent context made, therefore it is recommended the use of immutable data-types.

Lets picture a simple use case for this class, imagine that you need a way to track and centralize all the logs that happen in a request. AsyncLocal could be one option for this, you just need to assign a value at the beginning of the request and have an interceptor that enriches each log with the value initially.

But there is a catch! When persisting a value through asynchronous flows each new async context is isolated from its parent async context. So **the information that is being persisted across an asynchronous flow is only persisted down and not up, meaning that a parent context will never be aware of any child context modifications**.

AsyncLocal<T> is a class that enables us to persist a value through asynchronous flows but this persistence only happens from parent-to-child contexts.

## Ref
- https://nelsonparente.medium.com/a-little-riddle-with-asynclocal-1fd11322067f
- https://learn.microsoft.com/en-us/dotnet/api/system.threading.asynclocal-1?view=net-7.0