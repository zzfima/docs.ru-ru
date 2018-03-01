---
title: "Значения, возвращаемые методом Main() (Руководство по программированию на C#)"
ms.date: 08/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9f317879a4941adfd3d125c7697226f8a510254c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="5ca14-102">Значения, возвращаемые методом Main() (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5ca14-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="5ca14-103">Метод `Main` может возвращать значение `void`:</span><span class="sxs-lookup"><span data-stu-id="5ca14-103">The `Main` method can return `void`:</span></span>

[!code-csharp[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]

<span data-ttu-id="5ca14-104">Он также может возвращать значение типа `int`:</span><span class="sxs-lookup"><span data-stu-id="5ca14-104">It can also return an `int`:</span></span>

[!code-csharp[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]

<span data-ttu-id="5ca14-105">Если значение, возвращаемое методом `Main`, не используется, то указание в качестве возвращаемого типа `void` несколько упрощает код.</span><span class="sxs-lookup"><span data-stu-id="5ca14-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="5ca14-106">Однако возврат целого значения позволяет программе передавать информацию о своем состоянии другим программам и скриптам, которые вызывают исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="5ca14-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="5ca14-107">Возвращаемое значение `Main` рассматривается как код выхода процесса.</span><span class="sxs-lookup"><span data-stu-id="5ca14-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="5ca14-108">В приведенном ниже примере показано, как получить доступ к значению, возвращаемому методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="5ca14-108">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="5ca14-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5ca14-109">Example</span></span>

<span data-ttu-id="5ca14-110">В этом примере используются средства командной строки [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ca14-110">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="5ca14-111">Если вы не знакомы со средствами командной строки .NET Core, можете обратиться к [этому руководству по началу работы](../../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="5ca14-111">If you are unfamilar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="5ca14-112">Измените метод `Main` в файле *program.cs* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5ca14-112">Modify the `Main` method in *program.cs* as follows:</span></span>

[!code-csharp[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]

<span data-ttu-id="5ca14-113">При запуске программы в Windows значение, возвращаемое функцией `Main`, сохраняется в переменной среды.</span><span class="sxs-lookup"><span data-stu-id="5ca14-113">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="5ca14-114">Эту переменную можно получить из пакетного файла с помощью команды `ERRORLEVEL` или в PowerShell с помощью команды `$LastExitCode`.</span><span class="sxs-lookup"><span data-stu-id="5ca14-114">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="5ca14-115">Для сборки приложения можно выполнить команду `dotnet build` [интерфейса командной строки .NET](../../../core/tools/dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="5ca14-115">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="5ca14-116">Затем создайте сценарий PowerShell для запуска приложения и отображения результата.</span><span class="sxs-lookup"><span data-stu-id="5ca14-116">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="5ca14-117">Вставьте следующий код в текстовый файл и сохраните его под именем `test.ps1` в папке проекта.</span><span class="sxs-lookup"><span data-stu-id="5ca14-117">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="5ca14-118">Запустите сценарий PowerShell, набрав команду `test.ps1` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ca14-118">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="5ca14-119">Так как код возвращает нулевое значение, пакетный файл сообщает об успехе.</span><span class="sxs-lookup"><span data-stu-id="5ca14-119">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="5ca14-120">Но если изменить файл MainReturnValTest.cs, чтобы он возвращал ненулевое значение, и затем повторно скомпилировать программу, то при последующем выполнении сценария PowerShell будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5ca14-120">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="5ca14-121">Пример полученных результатов</span><span class="sxs-lookup"><span data-stu-id="5ca14-121">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="5ca14-122">Значения, возвращаемые асинхронным методом main</span><span class="sxs-lookup"><span data-stu-id="5ca14-122">Async Main return values</span></span>

<span data-ttu-id="5ca14-123">Возвращаемые значения асинхронного метода main перемещают стандартный код, необходимый для вызова асинхронных методов в `Main`, в код, созданный компилятором.</span><span class="sxs-lookup"><span data-stu-id="5ca14-123">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="5ca14-124">Ранее для вызова асинхронного кода и для запуска программы до завершения асинхронной операции приходилось использовать следующую конструкцию:</span><span class="sxs-lookup"><span data-stu-id="5ca14-124">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="5ca14-125">Теперь ее можно заменить на:</span><span class="sxs-lookup"><span data-stu-id="5ca14-125">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="5ca14-126">Преимущество нового синтаксиса состоит в том, что компилятор всегда формирует правильный код.</span><span class="sxs-lookup"><span data-stu-id="5ca14-126">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="5ca14-127">Код, созданный компилятором</span><span class="sxs-lookup"><span data-stu-id="5ca14-127">Compiler generated code</span></span>

<span data-ttu-id="5ca14-128">Если точка входа приложения возвращает `Task` или `Task<int>`, то компилятор создает новую точку входа, которая вызывает метод точки входа, объявленный в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="5ca14-128">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="5ca14-129">Предположим, что эта точка входа называется `$GeneratedMain`. В этом случае компилятор создает следующий код для этих точек входа:</span><span class="sxs-lookup"><span data-stu-id="5ca14-129">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="5ca14-130">`static Task Main()` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="5ca14-130">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="5ca14-131">`static Task Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="5ca14-131">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="5ca14-132">`static Task<int> Main()` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="5ca14-132">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="5ca14-133">`static Task<int> Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="5ca14-133">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="5ca14-134">Если бы в примерах использовался модификатор `async` метода `Main`, компилятор сформировал бы точно такой же код.</span><span class="sxs-lookup"><span data-stu-id="5ca14-134">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ca14-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5ca14-135">See also</span></span>
<span data-ttu-id="5ca14-136">[Руководство по программированию на C#](../../programming-guide/index.md)
[Справочник по C#](../index.md)
[Main() и аргументы командной строки](index.md)
[Руководство: отображение аргументов командной строки](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[Руководство: доступ к аргументам командной строки с помощью foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span><span class="sxs-lookup"><span data-stu-id="5ca14-136">[C# Programming Guide](../../programming-guide/index.md)
[C# Reference](../index.md)
[Main() and Command-Line Arguments](index.md)
[How to: Display Command Line Arguments](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span></span>
