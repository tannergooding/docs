---
title: Create a .NET Core console application using Visual Studio for Mac
description: Learn how to create a .NET Core console application using Visual Studio for Mac.
ms.date: 06/02/2020
---
# Tutorial: Create a .NET Core console application using Visual Studio for Mac

This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.

> [!NOTE]
> Your feedback is highly valued. There are two ways you can provide feedback to the development team on Visual Studio for Mac:
>
> * In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report. You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.
> * To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## Prerequisites

* [Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Select the option to install .NET Core. Installing Xamarin is optional for .NET Core development. For more information, see the following resources:

  * [Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).
  * [Supported macOS versions](../install/dependencies.md?pivots=os-macos).
  * [.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).

## Create the app

Create a .NET Core console app project named "HelloWorld".

1. Start Visual Studio for Mac.

1. Select **New** in the start window.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="New button on the Visual Studio for Mac Start screen":::

1. In the **New Project** dialog, select **App** under the **Web and Console** node. Select the **Console Application** template, and select **Next**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="New project templates list":::

1. In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Select Target Framework":::

1. Type "HelloWorld" for the **Project Name**, and select **Create**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Configure your new Console Application dialog":::

The template creates a simple "Hello World" application. It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!" in the terminal window.

The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application. Any command-line arguments supplied when the application is launched are available in the `args` array.

## Run the app

1. Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="The terminal shows Hello World!":::

1. Close the **Terminal** window.

## Enhance the app

Enhance the application to prompt the user for their name and display it along with the date and time.

1. In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   This code displays "What is your name?" in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key. It stores this string in a variable named `name`. It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`. Finally, it displays these values in the console window.

   The `\n` represents a newline character.

   The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string. The expression value is inserted into the string in place of the expression. This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).

1. Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.

1. Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal shows modified program output":::

1. Close the terminal.

## Next steps

In this tutorial, you created a .NET Core console application. In the next tutorial, you debug the app.

> [!div class="nextstepaction"]
> [Debug a .NET Core console application in Visual Studio](debugging-with-visual-studio-mac.md)
