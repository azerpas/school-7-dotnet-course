# Advanced C#

# Delegates

```csharp
public delegate int NumericAggregator(int left, int right);

public class Operator 
{
    public int Product(int left, int right) => left * right;
}

public static class Program
{
    static void Main(string[] args)
    {
        var program = new Operator();
        /* delegate here */
        NumericAggregator foo = program.Product();

        /* use of delegate */
        int result = foo(2, 3);
    }
}
```

# Extension methods
```csharp
public class SomeClass
{
    public int Product(int left, int right) => left * right;
}

/* Static Method and Class */

public static class Extensions
{
    public static int Square(this SomeClass someClass, int value) => someClass.Product(value, value);
}

{
    var someClass = new SomeClass();
    int result = someClass.Square(5)
}
```

# Yield
```csharp
static void Main()
{
    foreach (int i in Power(2,8))
    {
        Console.Write("{0} ", i);
    }
}

public static System.Collections.Generic.IEnumerable<int> Power(int number, int exponent)
{
    int result = 1;

    for (int i = 0; i < exponent; i++)
    {
        result = result * exponent;
        yield return result;
    }
}

// Output: 2 4 8 16 32 64 128 256
```

# Linq
## Filter
- Where
- Take
- Skip
- TakeWhile
- Except
- Distinct
## Transformation
- Select
- SelectMany
- Join
- GroupBy
- OrderBy
- OrderByDescending
## Operations
- ToArray
- ToList
- ToDictionnary
- First
- FirstOrDefault
- Single
- Any
- All
- Count
- Min
- Max
- Sum
- Average

# Nullable vs Non-Nullable
```xml
<Nullable>enable</Nullable>
```
in .project

```csharp
int no = 0; // Not nullable
int? yes = 1; // Nullable
```

# ref & out & in
## ref
Passed by reference
## out
