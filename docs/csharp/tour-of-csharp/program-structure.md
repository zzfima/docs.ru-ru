---
title: Структура программы в C#. Краткий обзор языка C#
description: Узнайте, из каких блоков составляется программа на C#
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156835"
---
# <a name="program-structure"></a><span data-ttu-id="7cb5b-103">Структура программы</span><span class="sxs-lookup"><span data-stu-id="7cb5b-103">Program Structure</span></span>

<span data-ttu-id="7cb5b-104">В C# основными понятиями организационной структуры являются ***программы***, ***пространства имен***, ***типы***, ***члены*** и ***сборки***.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="7cb5b-105">Программа на языке C# состоит из одного или нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="7cb5b-106">В программе объявляются типы, которые содержат члены. Эти типы можно организовать в пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="7cb5b-107">Примерами типов являются классы и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="7cb5b-108">К членам относятся поля, методы, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="7cb5b-109">При компиляции программы на C# упаковываются в сборки.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="7cb5b-110">Сборка — это файл, обычно с расширением `.exe` или `.dll`, если она реализует ***приложение*** или ***библиотеку***, соответственно.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="7cb5b-111">Вы можете создать проект библиотеки с именем *acme*, используя команду `dotnet new`:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="7cb5b-112">В этом проекте объявите класс с именем `Stack` в пространство имен `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="7cb5b-113">Полное имя этого класса: `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="7cb5b-114">Этот класс содержит несколько членов: поле с именем `top`, два метода с именами `Push` и `Pop`, а также вложенный класс с именем `Entry`.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="7cb5b-115">Класс `Entry`, в свою очередь, содержит три члена: поле с именем `next`, поле с именем `data` и конструктор.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="7cb5b-116">Команда:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-116">The command:</span></span>

```console
dotnet build
```

<span data-ttu-id="7cb5b-117">Результатом компиляции будет библиотека (код без точки входа `Main`), сохраненная в сборке с именем `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="7cb5b-118">Сборки содержат исполняемый код в виде инструкций промежуточного языка (IL) и символьную информацию в виде метаданных.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="7cb5b-119">Перед выполнением JIT-компилятор среды CLR .NET преобразует код IL в сборке в код, зависящий от процессора.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="7cb5b-120">Сборка полностью описывает сама себя и содержит весь код и метаданные, поэтому в C# не используются директивы `#include` и файлы заголовков.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="7cb5b-121">Чтобы использовать в программе C# открытые типы и члены, содержащиеся в определенной сборке, вам достаточно указать ссылку на эту сборку при компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="7cb5b-122">Например, эта программа использует класс `Acme.Collections.Stack` из сборки `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="7cb5b-123">Файл *CSPROJ* для проекта предыдущей программы должен содержать узел ссылки для компилятора C#, чтобы разрешить ссылки на классы в сборке `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="7cb5b-124">После его добавления команда `dotnet build` создает исполняемую сборку с именем `example.exe`, которая при запуске возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="7cb5b-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="7cb5b-125">В C# исходный текст программы можно хранить в нескольких исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="7cb5b-126">При компиляции многофайловой программы на C# все исходные файлы обрабатываются вместе, и все они могут свободно ссылаться друг на друга. По сути обработка выполняется так, как если бы все исходные файлы были объединены в один большой файл.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="7cb5b-127">В C# никогда не используются опережающие объявления, так как порядок объявления, за редким исключением, не играет никакой роли.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="7cb5b-128">В C# нет требований объявлять только один открытый тип в одном исходном файле, а также имя исходного файла не обязано совпадать с типом, объявляемом в этом файле.</span><span class="sxs-lookup"><span data-stu-id="7cb5b-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7cb5b-129">[Назад](index.md)
>[Вперед](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="7cb5b-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
