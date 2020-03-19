---
title: 'Учебник: Создание поставщика типов'
description: Узнайте, как создать свои собственные поставщики типов F-типа в F-3.0, изучив несколько простых поставщиков типов, чтобы проиллюстрировать основные концепции.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186123"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="339ee-103">Учебник: Создание поставщика типов</span><span class="sxs-lookup"><span data-stu-id="339ee-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="339ee-104">Механизм поставщика типов в F-фондявляется значительной частью его поддержки программирования, богатого информацией.</span><span class="sxs-lookup"><span data-stu-id="339ee-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="339ee-105">В этом учебнике объясняется, как создать свой собственный тип поставщиков, прогуливаясь вас через развитие нескольких простых поставщиков типа, чтобы проиллюстрировать основные понятия.</span><span class="sxs-lookup"><span data-stu-id="339ee-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="339ee-106">Для получения дополнительной информации о механизме [Type Providers](index.md)поставщика типов в F-сообщении см.</span><span class="sxs-lookup"><span data-stu-id="339ee-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="339ee-107">Экосистема F-класса содержит ряд поставщиков типовых услуг для широко используемых интернет- и корпоративных служб передачи данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="339ee-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="339ee-108">For example:</span></span>

- <span data-ttu-id="339ee-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) включает в себя поставщиков типов для форматов JSON, XML, CSV и HTML-документов.</span><span class="sxs-lookup"><span data-stu-id="339ee-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="339ee-110">[СЗЛ-Провайдер](https://fsprojects.github.io/SQLProvider/) обеспечивает сильно набрасываемый доступ к базам данных СЗЛ с помощью картирования объектов и запросов f- LIN' с этими источниками данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="339ee-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) имеет набор поставщиков типов для компиляции времени проверенного встраивания T-S'L в F.</span><span class="sxs-lookup"><span data-stu-id="339ee-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="339ee-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — это старый набор поставщиков типов для использования только с помощью программ .NET Framework для доступа к услугам данных S'L, Entity Framework, OData и WSDL.</span><span class="sxs-lookup"><span data-stu-id="339ee-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="339ee-113">При необходимости можно создавать поставщиков пользовательских типов или ссылаться на поставщиков типов, созданных другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="339ee-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="339ee-114">Например, в вашей организации может быть служба данных, которая обеспечивает большое и растущее число названных наборов данных, каждый из которых имеет свою собственную стабильную схему данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="339ee-115">Можно создать поставщика типов, который считывает схемы и представляет текущие наборы данных программисту в сильно набранном виде.</span><span class="sxs-lookup"><span data-stu-id="339ee-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="339ee-116">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="339ee-116">Before You Start</span></span>

<span data-ttu-id="339ee-117">Механизм поставщика типов в первую очередь предназначен для внедрения стабильных информационных пространств данных и услуг в опыт программирования F.</span><span class="sxs-lookup"><span data-stu-id="339ee-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="339ee-118">Этот механизм не предназначен для инъекционных информационных пространств, схема которых изменяется при выполнении программы способами, относящимися к логике программы.</span><span class="sxs-lookup"><span data-stu-id="339ee-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="339ee-119">Кроме того, механизм не предназначен для внутриязыкового метапрограммирования, даже если этот домен содержит некоторые допустимые применения.</span><span class="sxs-lookup"><span data-stu-id="339ee-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="339ee-120">Этот механизм следует использовать только в тех случаях, когда это необходимо и в тех случаях, когда разработка поставщика типа дает очень высокую ценность.</span><span class="sxs-lookup"><span data-stu-id="339ee-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="339ee-121">Следует избегать написания поставщика типов, где схема недоступна.</span><span class="sxs-lookup"><span data-stu-id="339ee-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="339ee-122">Аналогичным образом следует избегать написания поставщика типов, в котором достаточно обычной (или даже существующей) библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="339ee-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="339ee-123">Перед началом вы можете задать следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="339ee-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="339ee-124">У вас есть схема для вашего источника информации?</span><span class="sxs-lookup"><span data-stu-id="339ee-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="339ee-125">Если да, то что такое отображение в системе типов F и .NET?</span><span class="sxs-lookup"><span data-stu-id="339ee-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="339ee-126">Можно ли использовать существующий (динамически набранный) API в качестве отправной точки для реализации?</span><span class="sxs-lookup"><span data-stu-id="339ee-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="339ee-127">Будете ли вы и ваша организация имеют достаточно использует тип поставщика, чтобы сделать написание его стоит?</span><span class="sxs-lookup"><span data-stu-id="339ee-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="339ee-128">Удовлетворит ли нормальная библиотека .NET ваши потребности?</span><span class="sxs-lookup"><span data-stu-id="339ee-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="339ee-129">Насколько изменится ваша схема?</span><span class="sxs-lookup"><span data-stu-id="339ee-129">How much will your schema change?</span></span>

- <span data-ttu-id="339ee-130">Изменится ли она во время кодирования?</span><span class="sxs-lookup"><span data-stu-id="339ee-130">Will it change during coding?</span></span>

- <span data-ttu-id="339ee-131">Изменится ли она между сеансами кодирования?</span><span class="sxs-lookup"><span data-stu-id="339ee-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="339ee-132">Изменится ли она во время выполнения программы?</span><span class="sxs-lookup"><span data-stu-id="339ee-132">Will it change during program execution?</span></span>

<span data-ttu-id="339ee-133">Поставщики типов лучше всего подходят для ситуаций, когда схема стабильна во время выполнения и в течение всего срока службы компилированного кода.</span><span class="sxs-lookup"><span data-stu-id="339ee-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="339ee-134">Поставщик простого типа</span><span class="sxs-lookup"><span data-stu-id="339ee-134">A Simple Type Provider</span></span>

<span data-ttu-id="339ee-135">Этот образец Sample.HelloWorldTypeProvider, похожий `examples` на образцы в каталоге [поставщика F' Type SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="339ee-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="339ee-136">Поставщик предоставляет "пространство типа", которое содержит 100 стертых типов, как показано в следующем коде, используя `Type1`синтаксис подписи F и опуская детали для всех, кроме.</span><span class="sxs-lookup"><span data-stu-id="339ee-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="339ee-137">Для получения дополнительной информации о стертых типах смотрите [Подробная информация о стыковых предоставленных типах](#details-about-erased-provided-types) позже в этой теме.</span><span class="sxs-lookup"><span data-stu-id="339ee-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="339ee-138">Обратите внимание, что набор представленных типов и элементов статично известен.</span><span class="sxs-lookup"><span data-stu-id="339ee-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="339ee-139">Этот пример не использует способность провайдеров предоставлять типы, зависят от схемы.</span><span class="sxs-lookup"><span data-stu-id="339ee-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="339ee-140">Реализация поставщика типов изложена в следующем коде, а детали описаны в более поздних разделах этой темы.</span><span class="sxs-lookup"><span data-stu-id="339ee-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="339ee-141">Между этим кодом и онлайн-образцами могут быть различия.</span><span class="sxs-lookup"><span data-stu-id="339ee-141">There may be differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

<span data-ttu-id="339ee-142">Чтобы использовать этот провайдер, откройте отдельный экземпляр Visual Studio, создайте скрипт F,, а затем добавьте ссылку на провайдера из вашего скрипта, используя #r как показано следующее код:</span><span class="sxs-lookup"><span data-stu-id="339ee-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="339ee-143">Затем ищите типы в пространстве `Samples.HelloWorldTypeProvider` имен, генерируемые поставщиком типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="339ee-144">Перед тем, как переоставить поставщика на перекомпилировать, убедитесь, что вы закрыли все экземпляры Visual Studio и F-Interactive, использующие поставщика DLL.</span><span class="sxs-lookup"><span data-stu-id="339ee-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="339ee-145">В противном случае произойдет ошибка сборки, поскольку вывод DLL будет заблокирован.</span><span class="sxs-lookup"><span data-stu-id="339ee-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="339ee-146">Чтобы отладить этот провайдер с помощью печатных заявлений, сделайте сценарий, который разоблачает проблему с поставщиком, а затем используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="339ee-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="339ee-147">Чтобы отладить этого поставщика с помощью Visual Studio, откройте командный запрос разработчика для Visual Studio с административными учетными данными и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="339ee-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="339ee-148">В качестве альтернативы откройте Visual Studio, откройте меню Debug, выберите `Debug/Attach to process…`и приложите к другому `devenv` процессу, где вы редактируете свой сценарий.</span><span class="sxs-lookup"><span data-stu-id="339ee-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="339ee-149">Используя этот метод, можно с легкостью настроить таргетинг на конкретную логику в поставщике типов, интерактивно введя выражения во второй экземпляр (с полным IntelliSense и другими функциями).</span><span class="sxs-lookup"><span data-stu-id="339ee-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="339ee-150">Можно отключить отладку Just My Code, чтобы лучше выявлять ошибки в генерируемом коде.</span><span class="sxs-lookup"><span data-stu-id="339ee-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="339ee-151">Для получения информации о том, как включить или отключить эту функцию, [см. Навигация по Коду с Debugger.](/visualstudio/debugger/navigating-through-code-with-the-debugger)</span><span class="sxs-lookup"><span data-stu-id="339ee-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="339ee-152">Кроме того, вы также можете установить `Debug` первое исключение, открыв меню, а затем `Exceptions` выбрав `Exceptions` или выбрав ключи Ctrl-Alt-E, чтобы открыть диалоговую коробку.</span><span class="sxs-lookup"><span data-stu-id="339ee-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="339ee-153">В этом диалоговом `Common Language Runtime Exceptions`поле, `Thrown` под , выберите флажок.</span><span class="sxs-lookup"><span data-stu-id="339ee-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="339ee-154">Внедрение поставщика типов</span><span class="sxs-lookup"><span data-stu-id="339ee-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="339ee-155">Этот раздел проведет вас по основным разделам реализации поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="339ee-156">Во-первых, вы определяете тип для самого поставщика пользовательского типа:</span><span class="sxs-lookup"><span data-stu-id="339ee-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="339ee-157">Этот тип должен быть общедоступным, и вы должны пометить его атрибутом [TypeProvider,](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) чтобы компилятор распознавал поставщика типа, когда отдельный проект F's ссылается на сборку, содержащую тип.</span><span class="sxs-lookup"><span data-stu-id="339ee-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="339ee-158">Параметр *конфигурации* является необязательным и, если он присутствует, содержит контекстную информацию о конфигурации для экземпляра типа поставщика, который создает компилятор F-формата.</span><span class="sxs-lookup"><span data-stu-id="339ee-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="339ee-159">Далее вы реализуете интерфейс [ITypeProvider.](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f)</span><span class="sxs-lookup"><span data-stu-id="339ee-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="339ee-160">В этом случае тип `TypeProviderForNamespaces` из `ProvidedTypes` API используется в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="339ee-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="339ee-161">Этот тип помощника может обеспечить конечную коллекцию охотно предоставленных названий, каждое из которых непосредственно содержит конечное количество фиксированных, охотно предоставленных типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="339ee-162">В этом контексте поставщик *охотно* генерирует типы, даже если они не нужны или используются.</span><span class="sxs-lookup"><span data-stu-id="339ee-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="339ee-163">Затем определите локальные частные значения, определяющие пространство имен для предоставленных типов, и найдите саму сборку поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="339ee-164">Эта сборка позже используется в качестве логического родительского типа предоставленных типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="339ee-165">Затем создайте функцию для предоставления каждого из типов Type1... Тип100.</span><span class="sxs-lookup"><span data-stu-id="339ee-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="339ee-166">Эта функция объясняется более подробно позже в этой теме.</span><span class="sxs-lookup"><span data-stu-id="339ee-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="339ee-167">Далее, создайте 100 предоставленных типов:</span><span class="sxs-lookup"><span data-stu-id="339ee-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="339ee-168">Далее добавьте типы в виде предоставленного пространства имен:</span><span class="sxs-lookup"><span data-stu-id="339ee-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="339ee-169">Наконец, добавьте атрибут сборки, указывающий на то, что поставщик DLL создает тип:</span><span class="sxs-lookup"><span data-stu-id="339ee-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="339ee-170">Предоставление одного типа и его членов</span><span class="sxs-lookup"><span data-stu-id="339ee-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="339ee-171">Функция `makeOneProvidedType` выполняет реальную работу по предоставлению одного из типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="339ee-172">Этот шаг объясняет реализацию этой функции.</span><span class="sxs-lookup"><span data-stu-id="339ee-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="339ee-173">Во-первых, создайте предоставленный тип (например, Type1, когда n No 1 или Type57, когда n no 57).</span><span class="sxs-lookup"><span data-stu-id="339ee-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="339ee-174">Вы должны отметить следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="339ee-174">You should note the following points:</span></span>

- <span data-ttu-id="339ee-175">Этот при условии, что тип стирается.</span><span class="sxs-lookup"><span data-stu-id="339ee-175">This provided type is erased.</span></span>  <span data-ttu-id="339ee-176">Поскольку в компилированном коде указывается, что базовый тип — экземпляры `obj`будут отображаться как значения типа [obj.](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)</span><span class="sxs-lookup"><span data-stu-id="339ee-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="339ee-177">При указании невложенного типа необходимо указать пространство сборки и имя.</span><span class="sxs-lookup"><span data-stu-id="339ee-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="339ee-178">Для стертых типов сборка должна быть самой сборкой поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="339ee-179">Затем добавьте документацию XML в тип.</span><span class="sxs-lookup"><span data-stu-id="339ee-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="339ee-180">Эта документация задерживается, т.е. вычисляется по требованию, если она нужна компилятору хоста.</span><span class="sxs-lookup"><span data-stu-id="339ee-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="339ee-181">Далее вы добавляете предоставленное статическое свойство к типу:</span><span class="sxs-lookup"><span data-stu-id="339ee-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="339ee-182">Получение этого свойства всегда будет оценивать строку "Привет!".</span><span class="sxs-lookup"><span data-stu-id="339ee-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="339ee-183">Для `GetterCode` свойства используется цитата F-кода, которая представляет собой код, генерируемый компилятором хоста для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="339ee-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="339ee-184">Для получения дополнительной информации [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)о котировках см.</span><span class="sxs-lookup"><span data-stu-id="339ee-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="339ee-185">Добавьте в свойство документацию XML.</span><span class="sxs-lookup"><span data-stu-id="339ee-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="339ee-186">Теперь приложите предоставленное свойство к предоставленному типу.</span><span class="sxs-lookup"><span data-stu-id="339ee-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="339ee-187">Вы должны прикрепить предоставленного участника к одному типу.</span><span class="sxs-lookup"><span data-stu-id="339ee-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="339ee-188">В противном случае участник никогда не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="339ee-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="339ee-189">Теперь создайте предоставленный конструктор, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="339ee-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="339ee-190">Для `InvokeCode` конструктора возвращается цитата F-кода, которая представляет собой код, генерируемый компилятором хоста при вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="339ee-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="339ee-191">Например, можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="339ee-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="339ee-192">Экземпляр предоставленного типа будет создан с базовыми данными "Данные объекта".</span><span class="sxs-lookup"><span data-stu-id="339ee-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="339ee-193">Указанный код включает в себя преобразование в [obj,](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) потому что этот тип является стиранием этого при условии типа (как вы указали, когда вы объявили предоставленный тип).</span><span class="sxs-lookup"><span data-stu-id="339ee-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="339ee-194">Добавьте документацию XML к конструктору и добавьте предоставленный конструктор к предоставленному типу:</span><span class="sxs-lookup"><span data-stu-id="339ee-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="339ee-195">Создайте второй при условии, что конструктор принимает один параметр:</span><span class="sxs-lookup"><span data-stu-id="339ee-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="339ee-196">Для `InvokeCode` конструктора снова возвращается цитата F-кода, которая представляет собой код, созданный компилятором узла для вызова к методу.</span><span class="sxs-lookup"><span data-stu-id="339ee-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="339ee-197">Например, можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="339ee-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="339ee-198">Экземпляр предоставленного типа создается с базовыми данными "десять".</span><span class="sxs-lookup"><span data-stu-id="339ee-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="339ee-199">Возможно, вы уже `InvokeCode` заметили, что функция возвращает цитату.</span><span class="sxs-lookup"><span data-stu-id="339ee-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="339ee-200">Вход в эту функцию представляет собой список выражений, по одному на параметр конструктора.</span><span class="sxs-lookup"><span data-stu-id="339ee-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="339ee-201">В этом случае в `args.[0]`доступе является выражение, представляющее значение одного параметра.</span><span class="sxs-lookup"><span data-stu-id="339ee-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="339ee-202">Код для вызова к конструктору принуждает значение возврата к `obj`стертому типу.</span><span class="sxs-lookup"><span data-stu-id="339ee-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="339ee-203">После добавления второго предоставленного конструктора к типу создается свойство предоставленного экземпляра:</span><span class="sxs-lookup"><span data-stu-id="339ee-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="339ee-204">Получение этого свойства вернет длину строки, которая является объектом представления.</span><span class="sxs-lookup"><span data-stu-id="339ee-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="339ee-205">Свойство `GetterCode` возвращает цитату F-кода, которая определяет код, который генерирует компилятор хоста для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="339ee-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="339ee-206">Как, `InvokeCode` `GetterCode` функция возвращает цитату.</span><span class="sxs-lookup"><span data-stu-id="339ee-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="339ee-207">Компилятор хоста называет эту функцию списком аргументов.</span><span class="sxs-lookup"><span data-stu-id="339ee-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="339ee-208">В этом случае аргументы включают только одно выражение, представляющее экземпляр, на котором вызывается `args.[0]`геттер, к которому можно получить доступ с помощью .</span><span class="sxs-lookup"><span data-stu-id="339ee-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="339ee-209">Реализация `GetterCode` затем сращивания в цитату результата в `obj`стертом типе, и литые используется для удовлетворения механизма компилятора для проверки типов, что объект является строкой.</span><span class="sxs-lookup"><span data-stu-id="339ee-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="339ee-210">Следующая часть `makeOneProvidedType` предоставляет экземплярный метод с одним параметром.</span><span class="sxs-lookup"><span data-stu-id="339ee-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="339ee-211">Наконец, создайте вложенный тип, содержащий 100 вложенных свойств.</span><span class="sxs-lookup"><span data-stu-id="339ee-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="339ee-212">Создание этого вложенного типа и его свойства задерживается, то есть вычисляется по требованию.</span><span class="sxs-lookup"><span data-stu-id="339ee-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="339ee-213">Подробная информация о стереть предоставленные типы</span><span class="sxs-lookup"><span data-stu-id="339ee-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="339ee-214">Пример в этом разделе предоставляет только *стертые при условии типы,* которые особенно полезны в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="339ee-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="339ee-215">Когда вы пишете поставщику для информационного пространства, содержащего только данные и методы.</span><span class="sxs-lookup"><span data-stu-id="339ee-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="339ee-216">Когда вы пишете провайдера, где точная семантика типа выполнения не критична для практического использования информационного пространства.</span><span class="sxs-lookup"><span data-stu-id="339ee-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="339ee-217">Когда вы пишете поставщику для такого большого и взаимосвязанного информационного пространства, что технически невозможно создать реальные типы .NET для информационного пространства.</span><span class="sxs-lookup"><span data-stu-id="339ee-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="339ee-218">В этом примере каждый при `obj`условии, что тип стирается `obj` для ввода, и все виды использования типа будут отображаться как тип в скомпилированном коде.</span><span class="sxs-lookup"><span data-stu-id="339ee-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="339ee-219">На самом деле, основные объекты в этих примерах `System.Object` являются строками, но тип будет отображаться как в компилированном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="339ee-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="339ee-220">Как и во всех видах стирания типа, вы можете использовать явный бокс, распаковку и литье, чтобы подорвать стертые типы.</span><span class="sxs-lookup"><span data-stu-id="339ee-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="339ee-221">В этом случае недопустимое исключение литого, может привести к использованию объекта.</span><span class="sxs-lookup"><span data-stu-id="339ee-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="339ee-222">Время выполнения поставщика может определить свой собственный тип частного представления, чтобы защититься от ложных представлений.</span><span class="sxs-lookup"><span data-stu-id="339ee-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="339ee-223">Вы не можете определить стертые типы в самом F-из.</span><span class="sxs-lookup"><span data-stu-id="339ee-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="339ee-224">Только при условии, что типы могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="339ee-224">Only provided types may be erased.</span></span> <span data-ttu-id="339ee-225">Вы должны понимать последствия, как практические, так и семантические, использования либо стертых типов для поставщика типов, либо поставщика, предоставляющего стертые типы.</span><span class="sxs-lookup"><span data-stu-id="339ee-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="339ee-226">Стертый тип не имеет реального типа .NET.</span><span class="sxs-lookup"><span data-stu-id="339ee-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="339ee-227">Таким образом, вы не можете сделать точное отражение типа, и вы можете подорвать стертые типы, если вы используете отливки времени выполнения и другие методы, которые полагаются на точную семантику типа выполнения.</span><span class="sxs-lookup"><span data-stu-id="339ee-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="339ee-228">Подрыв стертых типов часто приводит к исключениям в водах во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="339ee-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="339ee-229">Выбор представлений для удаленных предоставленных типов</span><span class="sxs-lookup"><span data-stu-id="339ee-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="339ee-230">Для некоторых видов удалений, предоставленных, представление не требуется.</span><span class="sxs-lookup"><span data-stu-id="339ee-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="339ee-231">Например, вытиснутый при условии тип может содержать только статические свойства и элементы и отсутствие конструкторов, и никакие методы или свойства не возвращают экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="339ee-232">Если вы можете достичь экземпляров стертого предоставленного типа, необходимо рассмотреть следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="339ee-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="339ee-233">**Что такое стирание предоставленного типа?**</span><span class="sxs-lookup"><span data-stu-id="339ee-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="339ee-234">Стирание предоставленного типа — это то, как тип отображается в компилированном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="339ee-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="339ee-235">Удаление предоставленного стертого типа класса всегда является первым нестерированным базовым типом в цепочке наследования типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="339ee-236">Удаление предоставленного стертого типа интерфейса `System.Object`всегда.</span><span class="sxs-lookup"><span data-stu-id="339ee-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="339ee-237">**Каковы представления предоставленного типа?**</span><span class="sxs-lookup"><span data-stu-id="339ee-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="339ee-238">Набор возможных объектов для стертого при условии типа называется его представлениями.</span><span class="sxs-lookup"><span data-stu-id="339ee-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="339ee-239">В примере в этом документе представления всех стертых предоставленных типов `Type1..Type100` всегда являются объектами строки.</span><span class="sxs-lookup"><span data-stu-id="339ee-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="339ee-240">Все представления предоставленного типа должны быть совместимы с стиранием предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="339ee-241">(В противном случае, либо компилятор F's даст ошибку для использования поставщика типа, либо будет сгенерирован непроверяемый код .NET, который недействителен.</span><span class="sxs-lookup"><span data-stu-id="339ee-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="339ee-242">Поставщик типа не действителен, если он возвращает код, который дает представление, которое не является действительным.)</span><span class="sxs-lookup"><span data-stu-id="339ee-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="339ee-243">Вы можете выбрать представление для предоставленных объектов, используя любой из следующих подходов, оба из которых очень распространены:</span><span class="sxs-lookup"><span data-stu-id="339ee-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="339ee-244">Если вы просто предоставляете сильно набранную обертку по существующему типу .NET, часто имеет смысл, чтобы ваш тип стирал в этот тип, использовал экземпляры этого типа в качестве представлений или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="339ee-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="339ee-245">Этот подход является целесообразным, когда большинство существующих методов этого типа все еще имеет смысл при использовании сильно набранной версии.</span><span class="sxs-lookup"><span data-stu-id="339ee-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="339ee-246">Если требуется создать API, который значительно отличается от любого существующего API .NET, имеет смысл создать типы времени выполнения, которые будут стиранием типа и представлениями для предоставленных типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="339ee-247">Пример в этом документе использует строки в качестве представления предоставленных объектов.</span><span class="sxs-lookup"><span data-stu-id="339ee-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="339ee-248">Часто может быть целесообразным использовать другие объекты для представлений.</span><span class="sxs-lookup"><span data-stu-id="339ee-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="339ee-249">Например, вы можете использовать словарь в качестве пакета свойств:</span><span class="sxs-lookup"><span data-stu-id="339ee-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="339ee-250">В качестве альтернативы можно определить тип поставщика типов, который будет использоваться во время выполнения для формирования представления, а также одну или несколько операций выполнения:</span><span class="sxs-lookup"><span data-stu-id="339ee-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="339ee-251">Предоставленные участники могут построить экземпляры этого типа объекта:</span><span class="sxs-lookup"><span data-stu-id="339ee-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="339ee-252">В этом случае этот тип может использоваться в качестве стирания типа, указывая этот тип как `baseType` при `ProvidedTypeDefinition`построении:</span><span class="sxs-lookup"><span data-stu-id="339ee-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="339ee-253">Основные уроки</span><span class="sxs-lookup"><span data-stu-id="339ee-253">Key Lessons</span></span>

<span data-ttu-id="339ee-254">В предыдущем разделе объяснялось, как создать простой поставщик типов стирания, который предоставляет ряд типов, свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="339ee-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="339ee-255">В этом разделе также разъясняется концепция стирания типов, включая некоторые преимущества и недостатки предоставления стертых типов от поставщика типа, а также обсуждаются представления стертых типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="339ee-256">Поставщик типов, который использует статические параметры</span><span class="sxs-lookup"><span data-stu-id="339ee-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="339ee-257">Возможность параметризации поставщиков типов статичными данными позволяет использовать множество интересных сценариев, даже в тех случаях, когда поставщику не требуется доступ к каким-либо локальным или удаленным данным.</span><span class="sxs-lookup"><span data-stu-id="339ee-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="339ee-258">В этом разделе вы узнаете некоторые основные методы для воедино такой поставщик.</span><span class="sxs-lookup"><span data-stu-id="339ee-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="339ee-259">Тип Проверенный поставщик Regex</span><span class="sxs-lookup"><span data-stu-id="339ee-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="339ee-260">Представьте, что вы хотите реализовать поставщик типов для регулярных <xref:System.Text.RegularExpressions.Regex> выражений, который обертывает библиотеки .NET в интерфейс, который предоставляет следующие гарантии времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="339ee-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="339ee-261">Проверка допустимого регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="339ee-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="339ee-262">Предоставление названных свойств на совпадениях, основанных на любых именах групп в обычном выражении.</span><span class="sxs-lookup"><span data-stu-id="339ee-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="339ee-263">В этом разделе показано, как использовать `RegexTyped` поставщиков типов для создания типа, который параметры шаблона обычного выражения для предоставления этих преимуществ.</span><span class="sxs-lookup"><span data-stu-id="339ee-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="339ee-264">Компилятор сообщит об ошибке, если поставляемый шаблон недействителен, а поставщик типов может извлечь группы из шаблона, чтобы можно было получить к ним доступ с помощью именных свойств на совпадениях.</span><span class="sxs-lookup"><span data-stu-id="339ee-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="339ee-265">При проектировании поставщика типов следует учитывать, как его открытый API должен выглядеть для конечных пользователей и как этот дизайн будет переведен на код .NET.</span><span class="sxs-lookup"><span data-stu-id="339ee-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="339ee-266">В следующем примере показано, как использовать такой API для получения компонентов кода области:</span><span class="sxs-lookup"><span data-stu-id="339ee-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="339ee-267">Ниже приводится следующий пример, как поставщик типов переводит эти вызовы:</span><span class="sxs-lookup"><span data-stu-id="339ee-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="339ee-268">Обратите внимание на следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="339ee-268">Note the following points:</span></span>

- <span data-ttu-id="339ee-269">Стандартный тип Regex представляет `RegexTyped` параметризированный тип.</span><span class="sxs-lookup"><span data-stu-id="339ee-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="339ee-270">Конструктор `RegexTyped` приводит к вызову к конструктору Regex, переходя в аргумент статического типа для шаблона.</span><span class="sxs-lookup"><span data-stu-id="339ee-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="339ee-271">Результаты метода `Match` представлены стандартным <xref:System.Text.RegularExpressions.Match> типом.</span><span class="sxs-lookup"><span data-stu-id="339ee-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="339ee-272">Каждая названная группа приводит к предоставленному свойству, а доступ к свойству `Groups` приводит к использованию указателя в коллекции совпадения.</span><span class="sxs-lookup"><span data-stu-id="339ee-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="339ee-273">Следующий код является ядром логики для реализации такого поставщика, и этот пример не дает прибавления всех членов к предоставленному типу.</span><span class="sxs-lookup"><span data-stu-id="339ee-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="339ee-274">Для получения информации о каждом добавленном участнике, см.</span><span class="sxs-lookup"><span data-stu-id="339ee-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="339ee-275">Для получения полного кода, скачать образец из [F' 3.0 Пример пакета](https://archive.codeplex.com/?p=fsharp3sample) на веб-сайте CodePlex.</span><span class="sxs-lookup"><span data-stu-id="339ee-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="339ee-276">Обратите внимание на следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="339ee-276">Note the following points:</span></span>

- <span data-ttu-id="339ee-277">Поставщик типа принимает два статических `pattern`параметра: обязательное `options`значение , и необязательное значение (поскольку предусмотрено значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="339ee-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="339ee-278">После того, как статические аргументы поставляются, вы создаете экземпляр регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="339ee-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="339ee-279">Этот экземпляр будет выкидывать исключение, если Regex недоформирован, и эта ошибка будет сообщена пользователям.</span><span class="sxs-lookup"><span data-stu-id="339ee-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="339ee-280">В `DefineStaticParameters` рамках обратного вызова вы определяете тип, который будет возвращен после поступления аргументов.</span><span class="sxs-lookup"><span data-stu-id="339ee-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="339ee-281">Этот код `HideObjectMethods` соответствует действительности, так что опыт IntelliSense будет оставаться рационализированным.</span><span class="sxs-lookup"><span data-stu-id="339ee-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="339ee-282">Этот атрибут `Equals`приводит `GetHashCode` `Finalize`к `GetType` тому, что , , и члены будут подавлены из списков IntelliSense для предоставленного объекта.</span><span class="sxs-lookup"><span data-stu-id="339ee-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="339ee-283">Вы `obj` используете в качестве базового типа метода, но вы будете использовать `Regex` объект в качестве представления времени выполнения этого типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="339ee-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="339ee-284">Вызов к `Regex` конструктору бросает, <xref:System.ArgumentException> когда обычное выражение не является действительным.</span><span class="sxs-lookup"><span data-stu-id="339ee-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="339ee-285">Компилятор ловит это исключение и сообщает сообщение об ошибке пользователю во время компиляции или в редакторе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="339ee-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="339ee-286">Это исключение позволяет проверять регулярные выражения без запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="339ee-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="339ee-287">Тип, указанный выше, пока не полезен, поскольку не содержит значимых методов или свойств.</span><span class="sxs-lookup"><span data-stu-id="339ee-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="339ee-288">Во-первых, `IsMatch` добавьте статический метод:</span><span class="sxs-lookup"><span data-stu-id="339ee-288">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

<span data-ttu-id="339ee-289">Предыдущий код определяет `IsMatch`метод, который принимает строку в `bool`качестве ввода и возвращает .</span><span class="sxs-lookup"><span data-stu-id="339ee-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="339ee-290">Единственной сложной частью является `args` использование `InvokeCode` аргумента в определении.</span><span class="sxs-lookup"><span data-stu-id="339ee-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="339ee-291">В этом `args` примере приводится список цитат, представляющих аргументы к данному методу.</span><span class="sxs-lookup"><span data-stu-id="339ee-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="339ee-292">Если метод является методом экземпляра, `this` первый аргумент представляет аргумент.</span><span class="sxs-lookup"><span data-stu-id="339ee-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="339ee-293">Однако для статического метода аргументы являются лишь явными аргументами в пользу метода.</span><span class="sxs-lookup"><span data-stu-id="339ee-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="339ee-294">Обратите внимание, что тип указанного значения должен соответствовать `bool`указанному типу возврата (в данном случае).</span><span class="sxs-lookup"><span data-stu-id="339ee-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="339ee-295">Также обратите внимание, `AddXmlDoc` что этот код использует метод, чтобы убедиться, что предоставленный метод также имеет полезную документацию, которую можно предоставить через IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="339ee-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="339ee-296">Затем добавьте метод матча экземпляра.</span><span class="sxs-lookup"><span data-stu-id="339ee-296">Next, add an instance Match method.</span></span> <span data-ttu-id="339ee-297">Однако этот метод должен вернуть `Match` значение предоставленного типа, с тем чтобы к группам можно было получить доступ в строго модном виде.</span><span class="sxs-lookup"><span data-stu-id="339ee-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="339ee-298">Таким образом, вы `Match` сначала объявляете тип.</span><span class="sxs-lookup"><span data-stu-id="339ee-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="339ee-299">Поскольку этот тип зависит от шаблона, который был представлен в качестве статического аргумента, этот тип должен быть вложен в определение параметризированного типа:</span><span class="sxs-lookup"><span data-stu-id="339ee-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="339ee-300">Затем в тип матча добавляется одно свойство для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="339ee-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="339ee-301">Во время выполнения совпадение представлено как <xref:System.Text.RegularExpressions.Match> значение, поэтому цитата, определяющая свойство, должна использовать <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство для получения соответствующей группы.</span><span class="sxs-lookup"><span data-stu-id="339ee-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

<span data-ttu-id="339ee-302">Опять же, обратите внимание, что вы добавляете документацию XML в предоставленное свойство.</span><span class="sxs-lookup"><span data-stu-id="339ee-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="339ee-303">Также обратите внимание, что свойство может быть прочитано, если `GetterCode` `SetterCode` функция предоставлена, и свойство может быть написано, если функция предоставляется, так что полученное свойство читается только.</span><span class="sxs-lookup"><span data-stu-id="339ee-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="339ee-304">Теперь можно создать метод экземпляра, `Match` который возвращает значение этого типа:</span><span class="sxs-lookup"><span data-stu-id="339ee-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

<span data-ttu-id="339ee-305">Поскольку вы создаете `args.[0]` метод `RegexTyped` экземпляра, представляет экземпляр, на `args.[1]` котором вызывается метод, и является аргументом ввода.</span><span class="sxs-lookup"><span data-stu-id="339ee-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="339ee-306">Наконец, предоставьте конструктор, чтобы можно было создать экземпляры предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="339ee-307">Конструктор просто стирает к созданию стандартного экземпляра .NET Regex, который `obj` снова привозится к объекту, потому что это удаление предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="339ee-308">С этим изменением использование API-образца, указанное ранее в теме, работает как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="339ee-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="339ee-309">Следующий код является полным и окончательным:</span><span class="sxs-lookup"><span data-stu-id="339ee-309">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a><span data-ttu-id="339ee-310">Основные уроки</span><span class="sxs-lookup"><span data-stu-id="339ee-310">Key Lessons</span></span>

<span data-ttu-id="339ee-311">В этом разделе объясняется, как создать поставщика типов, который работает по его статическим параметрам.</span><span class="sxs-lookup"><span data-stu-id="339ee-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="339ee-312">Поставщик проверяет статический параметр и предоставляет операции в зависимости от его значения.</span><span class="sxs-lookup"><span data-stu-id="339ee-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="339ee-313">Поставщик типов, опирайся на локальные данные</span><span class="sxs-lookup"><span data-stu-id="339ee-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="339ee-314">Часто может потребоваться, чтобы поставщики типов представляли AI на основе не только статических параметров, но и информации из локальных или удаленных систем.</span><span class="sxs-lookup"><span data-stu-id="339ee-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="339ee-315">В этом разделе рассматриваются поставщики типов, основанные на локальных данных, таких как локальные файлы данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="339ee-316">Простой поставщик файлов CSV</span><span class="sxs-lookup"><span data-stu-id="339ee-316">Simple CSV File Provider</span></span>

<span data-ttu-id="339ee-317">В качестве простого примера рассмотрим поставщика типов для доступа к научным данным в формате Comma Separated Value (CSV).</span><span class="sxs-lookup"><span data-stu-id="339ee-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="339ee-318">В этом разделе предполагается, что файлы CSV содержат строку заголовка, за которой следуют данные о плавающей точке, так как следующая таблица иллюстрирует:</span><span class="sxs-lookup"><span data-stu-id="339ee-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="339ee-319">Расстояние (метр)</span><span class="sxs-lookup"><span data-stu-id="339ee-319">Distance (meter)</span></span>|<span data-ttu-id="339ee-320">Время (второй)</span><span class="sxs-lookup"><span data-stu-id="339ee-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="339ee-321">50.0</span><span class="sxs-lookup"><span data-stu-id="339ee-321">50.0</span></span>|<span data-ttu-id="339ee-322">3,7</span><span class="sxs-lookup"><span data-stu-id="339ee-322">3.7</span></span>|
|<span data-ttu-id="339ee-323">100.0</span><span class="sxs-lookup"><span data-stu-id="339ee-323">100.0</span></span>|<span data-ttu-id="339ee-324">5,2</span><span class="sxs-lookup"><span data-stu-id="339ee-324">5.2</span></span>|
|<span data-ttu-id="339ee-325">150.0</span><span class="sxs-lookup"><span data-stu-id="339ee-325">150.0</span></span>|<span data-ttu-id="339ee-326">6.4</span><span class="sxs-lookup"><span data-stu-id="339ee-326">6.4</span></span>|

<span data-ttu-id="339ee-327">В этом разделе показано, как предоставить тип, который `Distance` можно `float<meter>` использовать `Time` для получения `float<second>`строк с свойством типа и свойством типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="339ee-328">Для простоты сделаны следующие предположения:</span><span class="sxs-lookup"><span data-stu-id="339ee-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="339ee-329">Имена заголовков либо единицы меньше или имеют форму "Имя (единица)" и не содержат запятых.</span><span class="sxs-lookup"><span data-stu-id="339ee-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="339ee-330">Единицы все системы Международные (SI) единиц, как [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Модуль (F )](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) модуль определяет.</span><span class="sxs-lookup"><span data-stu-id="339ee-330">Units are all System International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="339ee-331">Единицы все простые (например, метр), а не соединения (например, метр в секунду).</span><span class="sxs-lookup"><span data-stu-id="339ee-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="339ee-332">Все столбцы содержат данные о плавающей точке.</span><span class="sxs-lookup"><span data-stu-id="339ee-332">All columns contain floating point data.</span></span>

<span data-ttu-id="339ee-333">Более полный поставщик ослабит эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="339ee-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="339ee-334">Опять же, первый шаг заключается в том, чтобы рассмотреть, как Должен выглядеть API.</span><span class="sxs-lookup"><span data-stu-id="339ee-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="339ee-335">Учитывая `info.csv` файл с содержимым из предыдущей таблицы (в формате, разделенном запятой), пользователи провайдера должны иметь возможность писать код, напоминающий следующий пример:</span><span class="sxs-lookup"><span data-stu-id="339ee-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="339ee-336">В этом случае компилятор должен преобразовать эти вызовы в нечто вроде следующего примера:</span><span class="sxs-lookup"><span data-stu-id="339ee-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="339ee-337">Оптимальный перевод потребует от поставщика `CsvFile` типа определения реального типа в сборке поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="339ee-338">Поставщики типов часто полагаются на несколько типов и методов помощника для обертывания важной логики.</span><span class="sxs-lookup"><span data-stu-id="339ee-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="339ee-339">Поскольку измерения стираются во время `float[]` выполнения, можно использовать в качестве стертого типа для строки.</span><span class="sxs-lookup"><span data-stu-id="339ee-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="339ee-340">Компилятор будет рассматривать различные столбцы как имеющие различные типы измерений.</span><span class="sxs-lookup"><span data-stu-id="339ee-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="339ee-341">Например, первый столбец в `float<meter>`нашем примере `float<second>`имеет тип, а второй имеет .</span><span class="sxs-lookup"><span data-stu-id="339ee-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="339ee-342">Однако стертое представление может оставаться довольно простым.</span><span class="sxs-lookup"><span data-stu-id="339ee-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="339ee-343">Следующий код показывает ядро реализации.</span><span class="sxs-lookup"><span data-stu-id="339ee-343">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="339ee-344">Обратите внимание на следующие моменты реализации:</span><span class="sxs-lookup"><span data-stu-id="339ee-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="339ee-345">Перегруженные конструкторы позволяют читать либо исходный файл, либо тот, который имеет идентичную схему.</span><span class="sxs-lookup"><span data-stu-id="339ee-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="339ee-346">Этот шаблон является общим, когда вы пишете поставщик типа для локальных или удаленных источников данных, и этот шаблон позволяет использовать локальный файл в качестве шаблона для удаленных данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="339ee-347">Для решения относительных имен файлов можно использовать значение [TypeProviderConfig,](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) передаваемые конструктору поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="339ee-348">Этот `AddDefinitionLocation` метод можно использовать для определения местоположения предоставленных свойств.</span><span class="sxs-lookup"><span data-stu-id="339ee-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="339ee-349">Поэтому, если `Go To Definition` вы используете на предоставленном свойстве, файл CSV откроется в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="339ee-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="339ee-350">Этот `ProvidedMeasureBuilder` тип можно использовать для поиска единиц СИ `float<_>` и создания соответствующих типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="339ee-351">Основные уроки</span><span class="sxs-lookup"><span data-stu-id="339ee-351">Key Lessons</span></span>

<span data-ttu-id="339ee-352">В этом разделе объясняется, как создать поставщика типов для локального источника данных с помощью простой схемы, содержащейся в самом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="339ee-353">Дальнейшая работа</span><span class="sxs-lookup"><span data-stu-id="339ee-353">Going Further</span></span>

<span data-ttu-id="339ee-354">Следующие разделы содержат предложения по дальнейшему изучению.</span><span class="sxs-lookup"><span data-stu-id="339ee-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="339ee-355">Взгляд на составленный код для стертых типов</span><span class="sxs-lookup"><span data-stu-id="339ee-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="339ee-356">Чтобы дать вам некоторое представление о том, как использование поставщика типа соответствует испускаемому коду, посмотрите на следующую функцию, используя `HelloWorldTypeProvider` используемую ранее в этой теме.</span><span class="sxs-lookup"><span data-stu-id="339ee-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="339ee-357">Вот изображение полученного кода, декомпилированного с помощью ildasm.exe:</span><span class="sxs-lookup"><span data-stu-id="339ee-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="339ee-358">Как показано в примере, все `Type1` упоминания `InstanceProperty` типа и свойства были удалены, оставляя только операции на типах времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="339ee-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="339ee-359">Конвенции по проектированию и именованию для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="339ee-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="339ee-360">Соблюдайте следующие конвенции при авторизации поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="339ee-361">**Поставщики протоколов о подключении** Как правило, имена большинства dL-услуг поставщика для протоколов подключения к данным и службам, таких как соединения OData или S'L, должны заканчиваться `TypeProvider` или `TypeProviders`находиться под другими службами.</span><span class="sxs-lookup"><span data-stu-id="339ee-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="339ee-362">Например, используйте имя DLL, напоминающее следующую строку:</span><span class="sxs-lookup"><span data-stu-id="339ee-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="339ee-363">Убедитесь, что предоставленные типы являются участниками соответствующего пространства имен, и укажите протокол подключения, который вы реализовали:</span><span class="sxs-lookup"><span data-stu-id="339ee-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="339ee-364">**Поставщики коммунальных услуг для общего кодирования**.</span><span class="sxs-lookup"><span data-stu-id="339ee-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="339ee-365">Для поставщика утилиты типа, например для обычных выражений, поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="339ee-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="339ee-366">В этом случае предоставленный тип будет отображаться в соответствующем месте в соответствии с обычными конвенциями о проектировании .NET:</span><span class="sxs-lookup"><span data-stu-id="339ee-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="339ee-367">**Синглтон Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="339ee-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="339ee-368">Некоторые поставщики типов подключаются к единому специализированному источнику данных и предоставляют только данные.</span><span class="sxs-lookup"><span data-stu-id="339ee-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="339ee-369">В этом случае следует `TypeProvider` отказаться от суффикса и использовать обычные условности для именования .NET:</span><span class="sxs-lookup"><span data-stu-id="339ee-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="339ee-370">Для получения дополнительной `GetConnection` информации, см. дизайн конвенции, которые описаны позже в этой теме.</span><span class="sxs-lookup"><span data-stu-id="339ee-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="339ee-371">Шаблоны проектирования для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="339ee-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="339ee-372">В следующих разделах описаны шаблоны проектирования, которые можно использовать при авторизации поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="339ee-373">Шаблон проектирования GetConnection</span><span class="sxs-lookup"><span data-stu-id="339ee-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="339ee-374">Большинство поставщиков типов должны быть `GetConnection` написаны для использования шаблона, используемого поставщиками типов в FSharp.Data.TypeProviders.dll, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="339ee-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="339ee-375">Поставщики типов, поддерживаемые удаленными данными и службами</span><span class="sxs-lookup"><span data-stu-id="339ee-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="339ee-376">Прежде чем создать поставщика типов, опирайся на удаленные данные и службы, необходимо рассмотреть ряд проблем, присущих подключенному программированию.</span><span class="sxs-lookup"><span data-stu-id="339ee-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="339ee-377">Эти вопросы включают следующие соображения:</span><span class="sxs-lookup"><span data-stu-id="339ee-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="339ee-378">схемы отображение</span><span class="sxs-lookup"><span data-stu-id="339ee-378">schema mapping</span></span>

- <span data-ttu-id="339ee-379">живость и недействительность при наличии изменения схемы</span><span class="sxs-lookup"><span data-stu-id="339ee-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="339ee-380">кэширование схемы</span><span class="sxs-lookup"><span data-stu-id="339ee-380">schema caching</span></span>

- <span data-ttu-id="339ee-381">асинхронные реализации операций доступа к данным</span><span class="sxs-lookup"><span data-stu-id="339ee-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="339ee-382">поддержка запросов, в том числе запросов LIN</span><span class="sxs-lookup"><span data-stu-id="339ee-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="339ee-383">учетные данные и аутентификация</span><span class="sxs-lookup"><span data-stu-id="339ee-383">credentials and authentication</span></span>

<span data-ttu-id="339ee-384">Эта тема не исследует эти вопросы дальше.</span><span class="sxs-lookup"><span data-stu-id="339ee-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="339ee-385">Дополнительные методы авторизации</span><span class="sxs-lookup"><span data-stu-id="339ee-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="339ee-386">При написании собственных поставщиков типов можно использовать следующие дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="339ee-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="339ee-387">Создание типов и участников по запросу</span><span class="sxs-lookup"><span data-stu-id="339ee-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="339ee-388">API ProvidedType задержал версии AddMember.</span><span class="sxs-lookup"><span data-stu-id="339ee-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="339ee-389">Эти версии используются для создания пространств типов по запросу.</span><span class="sxs-lookup"><span data-stu-id="339ee-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="339ee-390">Предоставление типов массивов и общих моментов типа</span><span class="sxs-lookup"><span data-stu-id="339ee-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="339ee-391">Вы делаете предоставленные члены (чьи подписи включают типы массивов, типы byref `MakeGenericType` и моментности <xref:System.Type>генерических типов) с помощью нормального `MakeArrayType`, `MakePointerType`и на любом экземпляре , включая `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="339ee-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="339ee-392">В некоторых случаях вам, возможно, `ProvidedTypeBuilder.MakeGenericType`придется использовать помощника в .</span><span class="sxs-lookup"><span data-stu-id="339ee-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="339ee-393">Для получения более подробной информации можно ознакомиться с [документацией поставщика услуг типа SDK.](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)</span><span class="sxs-lookup"><span data-stu-id="339ee-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="339ee-394">Предоставление аннотаций единицы измерения</span><span class="sxs-lookup"><span data-stu-id="339ee-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="339ee-395">API ProvidedTypes предоставляет помощникам для предоставления аннотаций измерения.</span><span class="sxs-lookup"><span data-stu-id="339ee-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="339ee-396">Например, чтобы уповатиться в типе, `float<kg>`используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="339ee-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="339ee-397">Чтобы обеспечить `Nullable<decimal<kg/m^2>>`тип, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="339ee-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="339ee-398">Доступ к ресурсам проекта-локальные или скриптно-локальные ресурсы</span><span class="sxs-lookup"><span data-stu-id="339ee-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="339ee-399">Каждому экземпляру поставщика типа `TypeProviderConfig` может быть присвоено значение во время строительства.</span><span class="sxs-lookup"><span data-stu-id="339ee-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="339ee-400">Это значение содержит папку «разрешение» для поставщика (т.е. папку проекта для компиляции или каталог, содержащий сценарий), список эталонных сборок и другую информацию.</span><span class="sxs-lookup"><span data-stu-id="339ee-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="339ee-401">Недействительности</span><span class="sxs-lookup"><span data-stu-id="339ee-401">Invalidation</span></span>

<span data-ttu-id="339ee-402">Поставщики могут поднимать недействительные сигналы, чтобы уведомить языковую службу F's о возможном изменении допущений схемы.</span><span class="sxs-lookup"><span data-stu-id="339ee-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="339ee-403">При возникновении недействительной проверки проверка типа переиздана, если провайдер размещается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="339ee-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="339ee-404">Этот сигнал будет проигнорирован, когда провайдер размещается в F- Interactive или на F'S Compiler (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="339ee-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="339ee-405">Кэшинг Схема Информация</span><span class="sxs-lookup"><span data-stu-id="339ee-405">Caching Schema Information</span></span>

<span data-ttu-id="339ee-406">Поставщики часто должны кэшировать доступ к информации о схеме.</span><span class="sxs-lookup"><span data-stu-id="339ee-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="339ee-407">Кэшированные данные должны храниться с помощью имени файла, приведенного в качестве статического параметра или в качестве пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="339ee-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="339ee-408">Примером кэширования схемы `LocalSchemaFile` является параметр в поставщике типов в сборке. `FSharp.Data.TypeProviders`</span><span class="sxs-lookup"><span data-stu-id="339ee-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="339ee-409">При реализации этих поставщиков этот статический параметр направляет поставщика типа на использование информации о схеме в указанном локальном файле вместо доступа к источнику данных по сети.</span><span class="sxs-lookup"><span data-stu-id="339ee-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="339ee-410">Чтобы использовать кэшированную информацию о схеме, `false`необходимо также установить статический параметр. `ForceUpdate`</span><span class="sxs-lookup"><span data-stu-id="339ee-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="339ee-411">Можно использовать аналогичный метод для обеспечения доступа к данным в режиме онлайн и в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="339ee-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="339ee-412">Поддержка Ассамблеи</span><span class="sxs-lookup"><span data-stu-id="339ee-412">Backing Assembly</span></span>

<span data-ttu-id="339ee-413">При компилировании файла `.dll` или `.exe` файла резервного копирования .dll для сгенерированных типов статически связан в полученную сборку.</span><span class="sxs-lookup"><span data-stu-id="339ee-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="339ee-414">Эта ссылка создается путем копирования определений типа промежуточного языка (IL) и любых управляемых ресурсов из резервной сборки в окончательную сборку.</span><span class="sxs-lookup"><span data-stu-id="339ee-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="339ee-415">При использовании F-Интерактивного файла поддержки .dll не копируется и вместо этого загружается непосредственно в интерактивный процесс F.'.</span><span class="sxs-lookup"><span data-stu-id="339ee-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="339ee-416">Исключения и диагностика от поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="339ee-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="339ee-417">Все виды использования всех членов из предоставленных типов могут выбросить исключения.</span><span class="sxs-lookup"><span data-stu-id="339ee-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="339ee-418">Во всех случаях, если поставщик типа бросает исключение, компилятор хоста приписывает ошибку определенному поставщику типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="339ee-419">Исключения поставщика типов никогда не должны приводить к внутренним ошибкам компилятора.</span><span class="sxs-lookup"><span data-stu-id="339ee-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="339ee-420">Поставщики типов не могут сообщать о предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="339ee-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="339ee-421">При размещении поставщика типов в компиляторе F-среды, среде разработки F-среды или F-Interactive все исключения из этого поставщика выявляются.</span><span class="sxs-lookup"><span data-stu-id="339ee-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="339ee-422">Свойство сообщения всегда является текстом ошибки, и не отображается след стека.</span><span class="sxs-lookup"><span data-stu-id="339ee-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="339ee-423">Если вы собираетесь бросить исключение, вы можете бросить `System.NotSupportedException` `System.IO.IOException`следующие примеры: , `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="339ee-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="339ee-424">Предоставление генерируемых типов</span><span class="sxs-lookup"><span data-stu-id="339ee-424">Providing Generated Types</span></span>

<span data-ttu-id="339ee-425">До сих пор в этом документе разъяснялось, как предоставлять стертые типы.</span><span class="sxs-lookup"><span data-stu-id="339ee-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="339ee-426">Вы также можете использовать механизм поставщика типов в F, чтобы обеспечить генерируемые типы, которые добавляются в качестве реальных определений типа .NET в программу пользователей.</span><span class="sxs-lookup"><span data-stu-id="339ee-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="339ee-427">Вы должны ссылаться на генерируемые типы с помощью определения типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="339ee-428">Вспомогательный код ProvidedTypes-0.2, врамкахный в выпуске F-3.0, имеет лишь ограниченную поддержку для предоставления генерируемых типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="339ee-429">Следующие утверждения должны быть верны для определения генерируемого типа:</span><span class="sxs-lookup"><span data-stu-id="339ee-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="339ee-430">Для параметра `isErased` нужно задать значение `false`.</span><span class="sxs-lookup"><span data-stu-id="339ee-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="339ee-431">Генерируемый тип должен быть добавлен `ProvidedAssembly()`в недавно построенный, который представляет собой контейнер для сгенерированных фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="339ee-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="339ee-432">Поставщик должен иметь сборку, которая имеет фактический резервный файл .NET .dll с соответствующим файлом .dll на диске.</span><span class="sxs-lookup"><span data-stu-id="339ee-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="339ee-433">Правила и ограничения</span><span class="sxs-lookup"><span data-stu-id="339ee-433">Rules and Limitations</span></span>

<span data-ttu-id="339ee-434">Когда вы пишете поставщики типов, имейте в виду следующие правила и ограничения.</span><span class="sxs-lookup"><span data-stu-id="339ee-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="339ee-435">Предоставляемые типы должны быть доступны</span><span class="sxs-lookup"><span data-stu-id="339ee-435">Provided types must be reachable</span></span>

<span data-ttu-id="339ee-436">Все предоставленные типы должны быть доступны из невложенных типов.</span><span class="sxs-lookup"><span data-stu-id="339ee-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="339ee-437">Невложенные типы даются в вызове `TypeProviderForNamespaces` к конструктору `AddNamespace`или вызове.</span><span class="sxs-lookup"><span data-stu-id="339ee-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="339ee-438">Например, если поставщик предоставляет `StaticClass.P : T`тип, необходимо убедиться, что T является либо невложенным типом, либо вложенным под один.</span><span class="sxs-lookup"><span data-stu-id="339ee-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="339ee-439">Например, некоторые поставщики имеют статический `DataTypes` класс, например, который содержит эти `T1, T2, T3, ...` типы.</span><span class="sxs-lookup"><span data-stu-id="339ee-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="339ee-440">В противном случае ошибка говорит, что была найдена ссылка на тип T в сборке А, но тип не может быть найден в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="339ee-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="339ee-441">Если эта ошибка появится, убедитесь, что все ваши подтипы могут быть достигнуты из типов поставщиков.</span><span class="sxs-lookup"><span data-stu-id="339ee-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="339ee-442">Примечание: `T1, T2, T3...` Эти типы называются типами *на лету.*</span><span class="sxs-lookup"><span data-stu-id="339ee-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="339ee-443">Не забудьте поместить их в доступное пространство имен или тип родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="339ee-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="339ee-444">Ограничения механизма поставщика типов</span><span class="sxs-lookup"><span data-stu-id="339ee-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="339ee-445">Механизм поставщика типов в F-фз имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="339ee-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="339ee-446">Базовая инфраструктура для поставщиков типов в F-поставщике не поддерживает при условии общих типов или общих методов.</span><span class="sxs-lookup"><span data-stu-id="339ee-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="339ee-447">Механизм не поддерживает вложенные типы со статическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="339ee-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="339ee-448">Советы по разработке</span><span class="sxs-lookup"><span data-stu-id="339ee-448">Development Tips</span></span>

<span data-ttu-id="339ee-449">В процессе разработки можно найти следующие советы:</span><span class="sxs-lookup"><span data-stu-id="339ee-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="339ee-450">Выполнить два экземпляра Visual Studio</span><span class="sxs-lookup"><span data-stu-id="339ee-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="339ee-451">Вы можете разработать поставщика типов в одном экземпляре и протестировать поставщика в другом, потому что тестовый IDE возьмет блокировку файла .dll, который предотвращает перестроение поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="339ee-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="339ee-452">Таким образом, необходимо закрыть второй экземпляр Visual Studio во время построения поставщика в первой инстанции, а затем повторно открыть второй экземпляр после того, как провайдер построен.</span><span class="sxs-lookup"><span data-stu-id="339ee-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="339ee-453">Поставщики типа debug с помощью вызовов fsc.exe</span><span class="sxs-lookup"><span data-stu-id="339ee-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="339ee-454">Вы можете вызвать поставщиков типов, используя следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="339ee-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="339ee-455">fsc.exe (компилятор командной строки F')</span><span class="sxs-lookup"><span data-stu-id="339ee-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="339ee-456">fsi.exe (Интерактивный компилятор ФЗ)</span><span class="sxs-lookup"><span data-stu-id="339ee-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="339ee-457">devenv.exe (Визуальная студия)</span><span class="sxs-lookup"><span data-stu-id="339ee-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="339ee-458">Вы часто можете отладить тип поставщиков легче всего, используя fsc.exe на файл тестового скрипта (например, script.fsx).</span><span class="sxs-lookup"><span data-stu-id="339ee-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="339ee-459">Можно запустить отладчик из командного запроса.</span><span class="sxs-lookup"><span data-stu-id="339ee-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="339ee-460">Вы можете использовать журнал печати до утилиза.</span><span class="sxs-lookup"><span data-stu-id="339ee-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="339ee-461">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="339ee-461">See also</span></span>

- [<span data-ttu-id="339ee-462">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="339ee-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="339ee-463">Поставщик типа SDK</span><span class="sxs-lookup"><span data-stu-id="339ee-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
