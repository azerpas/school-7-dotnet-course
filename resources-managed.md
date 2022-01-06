# Ressources managées et non-managées

## Garbage collector
Récupère la mémoire qui n'est plus utilisée par le programme.

## IDisposable
```csharp
class Cat : IDisposable
{ 
    public void Dispose()
    {
    // Libère les resources alloués
    }
}
```

```csharp
public static void Main()
{
    // ...
    using (var cat = new Cat());
    // ...
}
```

Pareil que

```csharp
public static void Main()
{
    // ...
    var cat = new Cat();
    try
    {
        // ...
    }
    finally
    {
        cat.Dispose();
    }
}
```