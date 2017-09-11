---
title: "Структура программы в C#. Краткий обзор языка C#"
description: "Узнайте, из каких блоков составляется программа на C#"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8f443f8458cd392c75e9787e612ca1cc3518c7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="program-structure"></a><span data-ttu-id="95e26-104">Структура программы</span><span class="sxs-lookup"><span data-stu-id="95e26-104">Program Structure</span></span>

<span data-ttu-id="95e26-105">В C# основными понятиями организационной структуры являются ***программы***, ***пространства имен***, ***типы***, ***члены*** и ***сборки***.</span><span class="sxs-lookup"><span data-stu-id="95e26-105">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="95e26-106">Программа на языке C# состоит из одного или нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="95e26-106">C# programs consist of one or more source files.</span></span> <span data-ttu-id="95e26-107">В программе объявляются типы, которые содержат члены. Эти типы можно организовать в пространства имен.</span><span class="sxs-lookup"><span data-stu-id="95e26-107">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="95e26-108">Примерами типов являются классы и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="95e26-108">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="95e26-109">К членам относятся поля, методы, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="95e26-109">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="95e26-110">При компиляции программы на C# упаковываются в сборки.</span><span class="sxs-lookup"><span data-stu-id="95e26-110">When C# programs are compiled, they are physically packaged into assemblies.</span></span> <span data-ttu-id="95e26-111">Сборка — это файл, обычно с расширением `.exe` или `.dll`, если она реализует ***приложение*** или ***библиотеку***, соответственно.</span><span class="sxs-lookup"><span data-stu-id="95e26-111">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="95e26-112">Этот пример кода объявляет класс с именем `Stack` в пространство имен с именем `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="95e26-112">The example declares a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

<span data-ttu-id="95e26-113">[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]</span><span class="sxs-lookup"><span data-stu-id="95e26-113">[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]</span></span>

<span data-ttu-id="95e26-114">Полное имя этого класса: `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="95e26-114">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="95e26-115">Этот класс содержит несколько членов: поле с именем `top`, два метода с именами `Push` и `Pop`, а также вложенный класс с именем `Entry`.</span><span class="sxs-lookup"><span data-stu-id="95e26-115">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="95e26-116">Класс `Entry`, в свою очередь, содержит три члена: поле с именем `next`, поле с именем `data` и конструктор.</span><span class="sxs-lookup"><span data-stu-id="95e26-116">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="95e26-117">Если мы сохраним исходный код этого примера в файле `acme.cs`, то для его компиляции нужно выполнить такую командную строку:</span><span class="sxs-lookup"><span data-stu-id="95e26-117">Assuming that the source code of the example is stored in the file `acme.cs`, the command line</span></span>

```
csc /t:library acme.cs
```

<span data-ttu-id="95e26-118">Результатом компиляции будет библиотека (код без точки входа `Main`), сохраненная в сборке с именем `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="95e26-118">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95e26-119">В приведенных выше примерах используется компилятор командной строки `csc` для C#.</span><span class="sxs-lookup"><span data-stu-id="95e26-119">The examples above use `csc` as the command line C# compiler.</span></span> <span data-ttu-id="95e26-120">Он существует в виде исполняемого файла Windows.</span><span class="sxs-lookup"><span data-stu-id="95e26-120">This compiler is a windows executable.</span></span> <span data-ttu-id="95e26-121">Чтобы использовать C# на других платформах, вам понадобятся средства для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95e26-121">To use C# across other platforms, you should use the tools for .NET Core.</span></span> <span data-ttu-id="95e26-122">Экосистема .NET Core использует `dotnet` CLI для управления сборкой из командной строки.</span><span class="sxs-lookup"><span data-stu-id="95e26-122">The .NET Core ecosystem uses the `dotnet` CLI to manage command line builds.</span></span> <span data-ttu-id="95e26-123">Она позволяет управлять зависимостями и вызывать компилятор C#.</span><span class="sxs-lookup"><span data-stu-id="95e26-123">This includes managing dependencies, and invoking the C# compiler.</span></span> <span data-ttu-id="95e26-124">[В этом руководстве](../../core/tutorials/using-with-xplat-cli.md) вы найдете полное описание средств для всех платформ, поддерживаемых .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95e26-124">See [this tutorial](../../core/tutorials/using-with-xplat-cli.md) for a full description of those tools on the platforms supported by .NET Core.</span></span>

<span data-ttu-id="95e26-125">Сборки содержат исполняемый код в виде инструкций промежуточного языка (IL) и символьную информацию в виде метаданных.</span><span class="sxs-lookup"><span data-stu-id="95e26-125">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="95e26-126">Перед выполнением сборки ее код на языке IL автоматически преобразуется в код для конкретного процессора. Эту задачу выполняет JIT-компилятор среды .NET CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="95e26-126">Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.</span></span>

<span data-ttu-id="95e26-127">Cборка полностью описывает сама себя и содержит весь код и метаданные, поэтому в C# не используются директивы `#include` и файлы заголовков.</span><span class="sxs-lookup"><span data-stu-id="95e26-127">Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="95e26-128">Чтобы использовать в программе C# открытые типы и члены, содержащиеся в определенной сборке, вам достаточно указать ссылку на эту сборку при компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="95e26-128">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="95e26-129">Например, эта программа использует класс `Acme.Collections.Stack` из сборки `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="95e26-129">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

<span data-ttu-id="95e26-130">[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]</span><span class="sxs-lookup"><span data-stu-id="95e26-130">[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]</span></span>

<span data-ttu-id="95e26-131">Если на момент компиляции `example.cs` программа хранится в файле `example.cs`, то ссылка на сборку acme.dll с использованием параметра компилятора /r будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="95e26-131">If the program is stored in the file `example.cs`, when `example.cs` is compiled, the acme.dll assembly can be referenced using the compiler’s /r option:</span></span>

```
csc /r:acme.dll example.cs
```

<span data-ttu-id="95e26-132">Эта команда создает исполняемую сборку с именем `example.exe`, которая при запуске возвращает такие данные:</span><span class="sxs-lookup"><span data-stu-id="95e26-132">This creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```
100
10
1
```

<span data-ttu-id="95e26-133">В C# исходный текст программы можно хранить в нескольких исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="95e26-133">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="95e26-134">При компиляции многофайловой программы на C# все исходные файлы обрабатываются вместе, и все они могут свободно ссылаться друг на друга. По сути обработка выполняется так, как если бы все исходные файлы были объединены в один большой файл.</span><span class="sxs-lookup"><span data-stu-id="95e26-134">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="95e26-135">В C# никогда не используются опережающие объявления, поскольку порядок объявления, за редким исключением, не играет никакой роли.</span><span class="sxs-lookup"><span data-stu-id="95e26-135">Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="95e26-136">В C# нет требований объявлять только один открытый тип в одном исходном файле, а также имя исходного файла не обязано совпадать с типом, объявляемом в этом файле.</span><span class="sxs-lookup"><span data-stu-id="95e26-136">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="95e26-137">[Назад](index.md)
[Вперед](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="95e26-137">[Previous](index.md)
[Next](types-and-variables.md)</span></span>

