# Threads

## Example

### Thread basic
```csharp
var thread = new Thread(() => 
{
    // ...
});

thread.Start();
thread.Join();
```

### Thread Pool
```csharp
ThreadPool.QueueUserWorkItem(() => 
{
    /// ...
})
```
- Groupe de threads réutilisable
- Nouveaux crées si besoin

## Lock 
```csharp
lock(x) { // x un objet
    // ...
} 
```

# Task
- P-e longue
- P-e asynchrone
## States
- Success
- Cancelled
- Failed

```csharp
var task = new Task(() => 
{
    /* ... */
});
task.Start();

var task2 = Task.Run(() => /*...*/);
```

## Members
- Wait
- Result
- WhenAll
- WhenAny

## Cancellation Token
```CancellationTokenSource```
- Thread Safe with methods:
```csharp
CancelAfter(timeout);
ThrowIfCancellationTokenRequested
```

## Volatile
```csharp
// keyword to hint to the compiler that data is accessed by multiple threads
private volatile bool _shouldStop;
```

## Interlocked
Atomic operations
```csharp
Interlocked.Increment(ref int location);
Interlocked.Add();
Interlocked.Exchange(ref T location, T val);
// ...
```

## ConcurrentDictionnary
```csharp
TryAdd();
TryUpdate(key, newValue, expected);
GetOrAdd();
AddOrUpdate();
```