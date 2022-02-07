# DSharpPlus

## Design Pattern: [Task-based Asynchronous Pattern](https://docs.microsoft.com/en-us/dotnet/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap)

---

### Program.cs setup

* "Due to the way the compiler generates the underlying IL code, marking our Main method as async has the potential to cause problems. As a result, we must pass the program execution to an async method."

```static void Main(string[] args)
{
    MainAsync().GetAwaiter().GetResult();
}

static async Task MainAsync()
{

}  
```

* To instantiate a new DiscordClient object, we need to provide a DiscordConfiguration object with config values

* We'll store these in a separate file called DiscordConfiguration.json, and map it to a C# object called DiscordConfiguration

* Note: when using another library's async methods,they need to be called with `await` operator

```using(var streamReader = new StreamReader(fileStream))
    {
        configJson = **await** streamReader.ReadToEndAsync();
    }
```
