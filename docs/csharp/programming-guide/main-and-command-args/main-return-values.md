---
title: Руководство по программированию на C#. Значения, возвращаемые методом Main()
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 21e780470f455ac133fd4d11ae43c63a4b18c582
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712043"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="71141-102">Значения, возвращаемые методом Main() (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="71141-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="71141-103">Метод `Main` может возвращать значение `void`:</span><span class="sxs-lookup"><span data-stu-id="71141-103">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="71141-104">Он также может возвращать значение типа `int`:</span><span class="sxs-lookup"><span data-stu-id="71141-104">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="71141-105">Если значение, возвращаемое методом `Main`, не используется, то указание в качестве возвращаемого типа `void` несколько упрощает код.</span><span class="sxs-lookup"><span data-stu-id="71141-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="71141-106">Однако возврат целого значения позволяет программе передавать информацию о своем состоянии другим программам и скриптам, которые вызывают исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="71141-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="71141-107">Возвращаемое значение `Main` рассматривается как код выхода процесса.</span><span class="sxs-lookup"><span data-stu-id="71141-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="71141-108">Если `void` возвращается из `Main`, код завершения будет неявно задан как `0`.</span><span class="sxs-lookup"><span data-stu-id="71141-108">If `void` is returned from `Main` the exit code will be implicitly `0`.</span></span> <span data-ttu-id="71141-109">В приведенном ниже примере показано, как получить доступ к значению, возвращаемому методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="71141-109">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="71141-110">Пример</span><span class="sxs-lookup"><span data-stu-id="71141-110">Example</span></span>

<span data-ttu-id="71141-111">В этом примере используются средства командной строки [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="71141-111">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="71141-112">Если вы не знакомы со средствами командной строки .NET Core, можете обратиться к [этому руководству по началу работы](../../../core/tutorials/cli-create-console-app.md).</span><span class="sxs-lookup"><span data-stu-id="71141-112">If you are unfamiliar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/cli-create-console-app.md).</span></span>

<span data-ttu-id="71141-113">Измените метод `Main` в файле *program.cs* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="71141-113">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="71141-114">При запуске программы в Windows значение, возвращаемое функцией `Main`, сохраняется в переменной среды.</span><span class="sxs-lookup"><span data-stu-id="71141-114">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="71141-115">Эту переменную можно получить из пакетного файла с помощью команды `ERRORLEVEL` или в PowerShell с помощью команды `$LastExitCode`.</span><span class="sxs-lookup"><span data-stu-id="71141-115">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="71141-116">Для сборки приложения можно выполнить команду `dotnet build` [интерфейса командной строки .NET](../../../core/tools/dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="71141-116">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="71141-117">Затем создайте сценарий PowerShell для запуска приложения и отображения результата.</span><span class="sxs-lookup"><span data-stu-id="71141-117">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="71141-118">Вставьте следующий код в текстовый файл и сохраните его под именем `test.ps1` в папке проекта.</span><span class="sxs-lookup"><span data-stu-id="71141-118">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="71141-119">Запустите сценарий PowerShell, набрав команду `test.ps1` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71141-119">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="71141-120">Так как код возвращает нулевое значение, пакетный файл сообщает об успехе.</span><span class="sxs-lookup"><span data-stu-id="71141-120">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="71141-121">Но если изменить файл MainReturnValTest.cs, чтобы он возвращал ненулевое значение, и затем повторно скомпилировать программу, то при последующем выполнении сценария PowerShell будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="71141-121">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

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

## <a name="sample-output"></a><span data-ttu-id="71141-122">Пример полученных результатов</span><span class="sxs-lookup"><span data-stu-id="71141-122">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="71141-123">Значения, возвращаемые асинхронным методом main</span><span class="sxs-lookup"><span data-stu-id="71141-123">Async Main return values</span></span>

<span data-ttu-id="71141-124">Возвращаемые значения асинхронного метода main перемещают стандартный код, необходимый для вызова асинхронных методов в `Main`, в код, созданный компилятором.</span><span class="sxs-lookup"><span data-stu-id="71141-124">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="71141-125">Ранее для вызова асинхронного кода и для запуска программы до завершения асинхронной операции приходилось использовать следующую конструкцию:</span><span class="sxs-lookup"><span data-stu-id="71141-125">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="71141-126">Теперь ее можно заменить на:</span><span class="sxs-lookup"><span data-stu-id="71141-126">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="71141-127">Преимущество нового синтаксиса состоит в том, что компилятор всегда формирует правильный код.</span><span class="sxs-lookup"><span data-stu-id="71141-127">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="71141-128">Код, созданный компилятором</span><span class="sxs-lookup"><span data-stu-id="71141-128">Compiler generated code</span></span>

<span data-ttu-id="71141-129">Если точка входа приложения возвращает `Task` или `Task<int>`, то компилятор создает новую точку входа, которая вызывает метод точки входа, объявленный в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="71141-129">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="71141-130">Предположим, что эта точка входа называется `$GeneratedMain`. В этом случае компилятор создает следующий код для этих точек входа:</span><span class="sxs-lookup"><span data-stu-id="71141-130">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="71141-131">`static Task Main()` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="71141-131">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="71141-132">`static Task Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="71141-132">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="71141-133">`static Task<int> Main()` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="71141-133">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="71141-134">`static Task<int> Main(string[])` приводит к тому, что компилятор формирует эквивалент `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="71141-134">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="71141-135">Если бы в примерах использовался модификатор `async` метода `Main`, компилятор сформировал бы точно такой же код.</span><span class="sxs-lookup"><span data-stu-id="71141-135">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="71141-136">См. также</span><span class="sxs-lookup"><span data-stu-id="71141-136">See also</span></span>

- [<span data-ttu-id="71141-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="71141-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="71141-138">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="71141-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71141-139">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="71141-139">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="71141-140">Отображение аргументов командной строки</span><span class="sxs-lookup"><span data-stu-id="71141-140">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
