---
title: Создание простой параллельной программы с использованием Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 0300f8900cd18159ba3a2170cfba96f302f282a0
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588139"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="d9bdb-102">Практическое руководство. написание простого цикла Parallel.ForEach</span><span class="sxs-lookup"><span data-stu-id="d9bdb-102">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="d9bdb-103">В этом примере показано, как использовать цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для включения параллелизма данных в любом источнике данных <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="d9bdb-104">В этой документации для определения делегатов в PLINQ используются лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="d9bdb-105">Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdb-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="d9bdb-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d9bdb-106">Example</span></span>

<span data-ttu-id="d9bdb-107">В этом примере предполагается, что у вас есть несколько JPG-файлов в папке *C:\Пользователи\Общие\Изображения\Образцы изображений* и что будет создана новая вложенная папка *Измененные*.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-107">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="d9bdb-108">При выполнении примера каждое изображение JPG в папке *Образцы изображений* будет повернуто и сохранено в папку *Измененные*.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-108">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="d9bdb-109">Эти два пути при необходимости можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-109">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="d9bdb-110">Цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> действует как цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-110">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="d9bdb-111">Цикл разделяет исходную коллекцию на секции и распределяет задачи по нескольким потокам с учетом доступной среды системы.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-111">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="d9bdb-112">Чем больше в системе процессоров, тем быстрее выполняются параллельные методы.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-112">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="d9bdb-113">Для некоторых исходных коллекций, в зависимости от размера источника и типа выполняемых работ, последовательный цикл может оказаться быстрее.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-113">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="d9bdb-114">Дополнительные сведения о производительности см. в статье [Потенциальные ошибки, связанные с параллелизмом данных и задач](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdb-114">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="d9bdb-115">Дополнительные сведения о параллельных циклах см. в статье [Практическое руководство. Написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdb-115">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="d9bdb-116">Чтобы применить <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> для неуниверсальной коллекции, вы можете преобразовать ее в универсальную коллекцию с помощью метода расширения <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-116">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="d9bdb-117">Также вы можете использовать Parallel LINQ (PLINQ) для параллельной обработки источников данных <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-117">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="d9bdb-118">PLINQ позволяет применять декларативный синтаксис запроса для описания поведения цикла.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-118">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="d9bdb-119">Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdb-119">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="d9bdb-120">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-120">Compile and run the code</span></span>

<span data-ttu-id="d9bdb-121">Код можно скомпилировать как консольное приложение для .NET Framework или .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-121">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="d9bdb-122">В Visual Studio существуют шаблоны консольных приложений Visual Basic и C# для Windows Desktop и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-122">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="d9bdb-123">В командной строке можно использовать команды .NET Core CLI (например, `dotnet new console` или `dotnet new console -lang vb`). Также вы можете создать файл и использовать компилятор командной строки для приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-123">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="d9bdb-124">Для проекта .NET Core необходимо сослаться на пакет NuGet **System.Drawing.Common**.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-124">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="d9bdb-125">В Visual Studio используйте диспетчер пакетов NuGet для установки пакета.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-125">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="d9bdb-126">Кроме того, вы можете добавить ссылку на пакет в файл \*.csproj или \*.vbproj:</span><span class="sxs-lookup"><span data-stu-id="d9bdb-126">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="d9bdb-127">Чтобы запустить консольное приложение .NET Core из командной строки, используйте `dotnet run` в папке, которая содержит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-127">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="d9bdb-128">Чтобы запустить консольное приложение из Visual Studio, нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="d9bdb-128">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9bdb-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d9bdb-129">See also</span></span>

- [<span data-ttu-id="d9bdb-130">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="d9bdb-130">Data parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="d9bdb-131">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="d9bdb-131">Parallel programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="d9bdb-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d9bdb-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
