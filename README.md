# Consoul

A simple C# .NET non-static wrapper around System.Console which (for now) just adds good color support.

## Inspired By

https://github.com/RMCKirby/ColorConsole

https://github.com/colored-console/colored-console/wiki/Quickstart

http://dejanstojanovic.net/aspnet/2015/may/powerconsole-extension-to-systemconsole/

http://stackoverflow.com/questions/5762491/how-to-print-color-in-console-using-system-out-println

http://serilog.net/

https://github.com/bendetat/mickeysmith/blob/master/src/JsonDatabaseTestbed/Cmd.cs

https://github.com/tristanmenzel

```C#
public class ColouredConsole:IDisposable
{
    private readonly ConsoleColor _previous;

    protected ColouredConsole(ConsoleColor color)
    {
        _previous = Console.ForegroundColor;
        Console.ForegroundColor = color;
    }

    public static ColouredConsole Red()
    {
        return new ColouredConsole(ConsoleColor.Red);
    }

    public void Dispose()
    {
        Console.ForegroundColor = _previous;
    }
}
```

```C#
using (ColouredConsole.Red())
{
    Console.WriteLine("Hello, is it me you're looking for?");
}
```

TODO: (Tod) More to come ;)
