---
title: 'Учебник: Создание поставщика типов (F #)'
description: 'Описание способов создания собственных поставщиков типов F # в F # 3.0, изучив несколько поставщиков простого типа, чтобы продемонстрировать основные понятия.'
keywords: visual f#, f#, функциональное программирование
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: b2e83218184bd1aef8258378485b99697cc8cf8d
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="b737e-104">Учебник: Создание поставщика типов</span><span class="sxs-lookup"><span data-stu-id="b737e-104">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="b737e-105">Механизм поставщика типов в языке F # имеет значительную часть его поддержка сведения широкие возможности программирования.</span><span class="sxs-lookup"><span data-stu-id="b737e-105">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="b737e-106">Этот учебник посвящен созданию собственных поставщиков типов посредством разработки из нескольких поставщиков простого типа, чтобы продемонстрировать основные понятия.</span><span class="sxs-lookup"><span data-stu-id="b737e-106">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="b737e-107">Дополнительные сведения о механизме поставщик типа F # см. в разделе [поставщиков типов](index.md).</span><span class="sxs-lookup"><span data-stu-id="b737e-107">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="b737e-108">Экосистема F # содержит ряд поставщиков типов для часто используемых Интернет и enterprise служб данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-108">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="b737e-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="b737e-109">For example:</span></span>

- <span data-ttu-id="b737e-110">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) включает поставщиков типов для JSON, XML, CSV и HTML документа форматы.</span><span class="sxs-lookup"><span data-stu-id="b737e-110">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="b737e-111">[SQLProvider](https://fsprojects.github.io/SQLProvider/) предоставляет строго типизированный доступ к базам данных SQL через сопоставление объектов и F # LINQ запросы к источникам данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-111">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="b737e-112">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) набор поставщиков типов для компиляции вернули внедрение T-SQL в языке F #.</span><span class="sxs-lookup"><span data-stu-id="b737e-112">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="b737e-113">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — старые ряд поставщиков типов для использования только с помощью программирования .NET Framework для доступа к службам данных SQL, Entity Framework, OData и WSDL.</span><span class="sxs-lookup"><span data-stu-id="b737e-113">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="b737e-114">При необходимости можно создать пользовательские поставщики типов или ссылаются на поставщики типов, созданных другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="b737e-114">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="b737e-115">Например ваша организация может иметь службу данных, которая предоставляет большое и возрастающее число именованных наборов данных, каждый из которых свой собственный стабильная схема данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-115">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="b737e-116">Можно создать поставщик типов, который считывает схемы и представляет текущее наборы данных программисту строго типизированным образом.</span><span class="sxs-lookup"><span data-stu-id="b737e-116">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="b737e-117">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="b737e-117">Before You Start</span></span>

<span data-ttu-id="b737e-118">Механизм поставщика типа в основном предназначен для вводится неизменных данных и службы информационных пространств опыт программирования F #.</span><span class="sxs-lookup"><span data-stu-id="b737e-118">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="b737e-119">Этот механизм не поддерживает внедрение информационных пространств, схема которой изменяется во время выполнения программы таким образом, относящиеся к программной логики.</span><span class="sxs-lookup"><span data-stu-id="b737e-119">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="b737e-120">Кроме того механизм не поддерживает внутри языка метапрограммирования, несмотря на то, что этот домен содержит некоторые допустимые варианты.</span><span class="sxs-lookup"><span data-stu-id="b737e-120">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="b737e-121">Этот механизм следует использовать только при необходимости и где разработки поставщик типа создает очень большое значение.</span><span class="sxs-lookup"><span data-stu-id="b737e-121">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="b737e-122">Следует создавать поставщик типа, где схема недоступна.</span><span class="sxs-lookup"><span data-stu-id="b737e-122">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="b737e-123">Аналогичным образом, следует создавать поставщик типа там, где обычных (или даже существующего) Библиотека .NET было бы достаточно.</span><span class="sxs-lookup"><span data-stu-id="b737e-123">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="b737e-124">Прежде чем начать, можно задать следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="b737e-124">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="b737e-125">У схемы для источника сведений?</span><span class="sxs-lookup"><span data-stu-id="b737e-125">Do you have a schema for your information source?</span></span> <span data-ttu-id="b737e-126">Если это так, что такое сопоставление в F # и системой типов .NET</span><span class="sxs-lookup"><span data-stu-id="b737e-126">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="b737e-127">Можно ли использовать существующие интерфейсы API (динамического типа) в качестве отправной точки для реализации?</span><span class="sxs-lookup"><span data-stu-id="b737e-127">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="b737e-128">Вы и ваша организация будет достаточно использует поставщик типа делает написание ее смысл?</span><span class="sxs-lookup"><span data-stu-id="b737e-128">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="b737e-129">Обычные библиотеки .NET удовлетворят вашим потребностям?</span><span class="sxs-lookup"><span data-stu-id="b737e-129">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="b737e-130">Сколько изменится схемы?</span><span class="sxs-lookup"><span data-stu-id="b737e-130">How much will your schema change?</span></span>

- <span data-ttu-id="b737e-131">Изменится во время кодирования?</span><span class="sxs-lookup"><span data-stu-id="b737e-131">Will it change during coding?</span></span>

- <span data-ttu-id="b737e-132">Изменится между кодирования сеансы?</span><span class="sxs-lookup"><span data-stu-id="b737e-132">Will it change between coding sessions?</span></span>

- <span data-ttu-id="b737e-133">Изменится во время выполнения программы?</span><span class="sxs-lookup"><span data-stu-id="b737e-133">Will it change during program execution?</span></span>

<span data-ttu-id="b737e-134">Поставщики типов являются наилучшим образом подходит для случаев, когда схема стабильный во время выполнения и в течение времени существования скомпилированного кода.</span><span class="sxs-lookup"><span data-stu-id="b737e-134">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="b737e-135">Поставщик простой тип</span><span class="sxs-lookup"><span data-stu-id="b737e-135">A Simple Type Provider</span></span>

<span data-ttu-id="b737e-136">Этот образец является Samples.HelloWorldTypeProvider, аналогично примеров в `examples` каталог [SDK поставщик типа F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="b737e-136">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="b737e-137">Поставщик делает доступными «тип space», содержащий 100 вместо удаленных типов, как показано в следующем коде, используя синтаксис подписи F # и пропуск подробные сведения для всех, кроме `Type1`.</span><span class="sxs-lookup"><span data-stu-id="b737e-137">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="b737e-138">Дополнительные сведения об удаленных типах см. в разделе [сведения о стереть предоставленные типы](#details-about-erased-provided-types) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b737e-138">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

    /// This is an instance property.
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

<span data-ttu-id="b737e-139">Обратите внимание, набор типов и членов, предоставляемых статически известен.</span><span class="sxs-lookup"><span data-stu-id="b737e-139">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="b737e-140">В этом примере не используют возможность поставщики предоставляют типы, зависящие от схемы.</span><span class="sxs-lookup"><span data-stu-id="b737e-140">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="b737e-141">В следующем коде представлен реализации поставщика типа и подробности описаны в следующих разделах этой статьи.</span><span class="sxs-lookup"><span data-stu-id="b737e-141">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="b737e-142">Возможно, различия между этим кодом и примеров в сети.</span><span class="sxs-lookup"><span data-stu-id="b737e-142">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="b737e-143">Чтобы использовать этот поставщик, откройте отдельный экземпляр Visual Studio, создание скрипта F # и затем добавьте ссылку на службу из скрипта с помощью #r, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="b737e-143">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="b737e-144">Выполните поиск типов в `Samples.HelloWorldTypeProvider` пространство имен, которое создается поставщик типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-144">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="b737e-145">Перед перекомпиляцией поставщик убедитесь, что закрыты все экземпляры Visual Studio и F # Interactive, использующих DLL-Библиотеки поставщика.</span><span class="sxs-lookup"><span data-stu-id="b737e-145">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="b737e-146">В противном случае возникает ошибка сборки будет возникать, так как выходные данные библиотеки DLL будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="b737e-146">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="b737e-147">Чтобы отладить этот поставщик с помощью инструкции print, скрипт, указывающий на проблему с поставщиком, а затем использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="b737e-147">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="b737e-148">Чтобы отладить этот поставщик с помощью Visual Studio, откройте командную строку Visual Studio с правами администратора и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b737e-148">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="b737e-149">Кроме того, откройте Visual Studio откройте меню "Отладка", выберите `Debug/Attach to process…`и присоединить к другому `devenv` процесса, где требуется изменить скрипт.</span><span class="sxs-lookup"><span data-stu-id="b737e-149">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="b737e-150">С помощью этого метода, можно точнее указывать определенной логики у поставщика типов, введя интерактивно выражения в второй экземпляр (с технологией IntelliSense и других функций).</span><span class="sxs-lookup"><span data-stu-id="b737e-150">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="b737e-151">Можно отключить только мой код отладки, чтобы облегчить поиск ошибок в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="b737e-151">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="b737e-152">Сведения о том, как включить или отключить эту функцию, в разделе [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="b737e-152">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="b737e-153">Кроме того, можно также задать исключения первого шанса, перехват, открыв `Debug` меню и затем выбрав `Exceptions` или нажав клавиши Ctrl + Alt + E, чтобы открыть `Exceptions` диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="b737e-153">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="b737e-154">В этом диалоговом окне в разделе `Common Language Runtime Exceptions`выберите `Thrown` флажок.</span><span class="sxs-lookup"><span data-stu-id="b737e-154">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="b737e-155">Реализация поставщика типов</span><span class="sxs-lookup"><span data-stu-id="b737e-155">Implementation of the Type Provider</span></span>

<span data-ttu-id="b737e-156">В этом разделе описывается основной части реализации поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-156">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="b737e-157">Во-первых определения типа для пользовательского типа самим поставщиком:</span><span class="sxs-lookup"><span data-stu-id="b737e-157">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="b737e-158">Этот тип должен быть открытым, и необходимо отметить его с [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) таким образом, компилятор распознает поставщика типов при отдельном проекте F # ссылается на сборку, содержащую тип.</span><span class="sxs-lookup"><span data-stu-id="b737e-158">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="b737e-159">*Config* является необязательным и, если он имеется, содержит сведения о экземпляр типа поставщика, который компилятор F # создает контекстные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b737e-159">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="b737e-160">Далее необходимо реализовать [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b737e-160">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="b737e-161">В этом случае используется `TypeProviderForNamespaces` из тип `ProvidedTypes` API в качестве базового типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-161">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="b737e-162">Этот вспомогательный тип можно предоставить на конечную коллекцию заранее предоставлена пространства имен, непосредственно каждый из которых содержит конечное количество предопределенных, заранее типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-162">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="b737e-163">В этом контексте, поставщик *заранее* создает типы, даже если они не требуется или не используется.</span><span class="sxs-lookup"><span data-stu-id="b737e-163">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="b737e-164">Затем определить локальной частной значения, которые определяют пространство имен для существующих и найти сборку поставщика в тип.</span><span class="sxs-lookup"><span data-stu-id="b737e-164">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="b737e-165">Эта сборка используется как логический родительский тип удаленных типов, которые предоставляются для более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b737e-165">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="b737e-166">Далее создайте функцию для предоставления каждого типа тип1... Type100.</span><span class="sxs-lookup"><span data-stu-id="b737e-166">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="b737e-167">Эта функция является более подробно далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b737e-167">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="b737e-168">Теперь можно создать 100 предоставляемых типов:</span><span class="sxs-lookup"><span data-stu-id="b737e-168">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="b737e-169">Добавьте типы указанного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b737e-169">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="b737e-170">Наконец добавьте атрибут сборки, которое указывает, что вы создаете DLL-Библиотека поставщика типа:</span><span class="sxs-lookup"><span data-stu-id="b737e-170">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="b737e-171">Предоставление одного типа и его членов</span><span class="sxs-lookup"><span data-stu-id="b737e-171">Providing One Type And Its Members</span></span>

<span data-ttu-id="b737e-172">`makeOneProvidedType` Функция не работает указать один из типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-172">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="b737e-173">Этот шаг описывается реализация этой функции.</span><span class="sxs-lookup"><span data-stu-id="b737e-173">This step explains the implementation of this function.</span></span> <span data-ttu-id="b737e-174">Сначала создайте предоставленный тип (например, тип 1, если n = 1 или Type57, когда n = 57).</span><span class="sxs-lookup"><span data-stu-id="b737e-174">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="b737e-175">Следует отметить следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="b737e-175">You should note the following points:</span></span>

- <span data-ttu-id="b737e-176">Это при условии, что тип удаляется.</span><span class="sxs-lookup"><span data-stu-id="b737e-176">This provided type is erased.</span></span>  <span data-ttu-id="b737e-177">Поскольку указывают, что базовый тип является `obj`, экземпляров будет отображаться в виде значения типа [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) в скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="b737e-177">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="b737e-178">При указании типа, не являющегося вложенным, необходимо указать сборку и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b737e-178">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="b737e-179">Для удаленных типов сборки должно быть самой сборки типа поставщика.</span><span class="sxs-lookup"><span data-stu-id="b737e-179">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="b737e-180">Добавьте XML-документации для типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-180">Next, add XML documentation to the type.</span></span> <span data-ttu-id="b737e-181">В этой документации задерживается, то есть, вычисляются по требованию, если компилятор узла она нужна.</span><span class="sxs-lookup"><span data-stu-id="b737e-181">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="b737e-182">Далее вы добавите предоставленный статическое свойство в тип:</span><span class="sxs-lookup"><span data-stu-id="b737e-182">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="b737e-183">При получении этого свойства всегда возвращают строку «Hello!».</span><span class="sxs-lookup"><span data-stu-id="b737e-183">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="b737e-184">`GetterCode` Для свойство использует F # предложение, которое представляет код, который создает компилятор узла для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="b737e-184">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="b737e-185">Дополнительные сведения о предложениях см. в разделе [Цитирование кода (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="b737e-185">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="b737e-186">Добавьте XML-документации в свойство.</span><span class="sxs-lookup"><span data-stu-id="b737e-186">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="b737e-187">Теперь подключиться предоставленного свойства в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="b737e-187">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="b737e-188">Необходимо добавить указанный элемент только один тип.</span><span class="sxs-lookup"><span data-stu-id="b737e-188">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="b737e-189">В противном случае, значение элемента никогда не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="b737e-189">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="b737e-190">Теперь можно создайте указанный конструктор, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="b737e-190">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="b737e-191">`InvokeCode` Для завершения работы конструктор возвращает F # предложение, которое представляет код, который компилятор узла приводит к возникновению ошибки при вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="b737e-191">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="b737e-192">Например можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="b737e-192">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="b737e-193">Экземпляр указанного типа создается с базовыми данными «Данные объекта».</span><span class="sxs-lookup"><span data-stu-id="b737e-193">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="b737e-194">Заключенные в кавычки код включает преобразование в [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) , так как этот тип является стирания это предоставленный тип (как при объявлении предоставленного типа указан).</span><span class="sxs-lookup"><span data-stu-id="b737e-194">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="b737e-195">Добавьте в конструктор XML-документации и добавьте указанный конструктор для предоставленного типа:</span><span class="sxs-lookup"><span data-stu-id="b737e-195">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="b737e-196">Создайте второй предоставленный конструктор, который принимает один параметр:</span><span class="sxs-lookup"><span data-stu-id="b737e-196">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="b737e-197">`InvokeCode` Для конструктора снова возвращает F # предложение, которое представляет код, созданный в компиляторе базовой среды для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="b737e-197">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="b737e-198">Например можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="b737e-198">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="b737e-199">Экземпляр указанного типа создается с базовыми данными «10».</span><span class="sxs-lookup"><span data-stu-id="b737e-199">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="b737e-200">Возможно, вы уже заметили, `InvokeCode` функция возвращает предложения.</span><span class="sxs-lookup"><span data-stu-id="b737e-200">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="b737e-201">Входные данные для этой функции — список выражений, по одной на каждый параметр конструктора.</span><span class="sxs-lookup"><span data-stu-id="b737e-201">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="b737e-202">В этом случае выражение, представляющее значение одного параметра доступна в `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="b737e-202">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="b737e-203">Код для вызова конструктора приводит возвращаемое значение в тип стертой `obj`.</span><span class="sxs-lookup"><span data-stu-id="b737e-203">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="b737e-204">После добавления второй конструктор указанного типа, можно создать свойство предоставленный экземпляр:</span><span class="sxs-lookup"><span data-stu-id="b737e-204">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="b737e-205">При получении этого свойства возвращается длина строки, которое является объектом представления.</span><span class="sxs-lookup"><span data-stu-id="b737e-205">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="b737e-206">`GetterCode` Свойство возвращает F # предложение, которое указывает код, который создает компилятор узла для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="b737e-206">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="b737e-207">Как `InvokeCode`, `GetterCode` функция возвращает предложения.</span><span class="sxs-lookup"><span data-stu-id="b737e-207">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="b737e-208">Компилятор узла вызывает эту функцию со списком аргументов.</span><span class="sxs-lookup"><span data-stu-id="b737e-208">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="b737e-209">В этом случае аргументы включать только одно выражение, представляющее экземпляр, на котором вызывается метод получения значения, к которому можно получить с помощью `args.[0]`. Реализация `GetterCode` затем получает эту предложениям результат, введите в удаленных `obj`, и использовать приведение для удовлетворения компилятора механизм для проверки типов, что объект является строкой.</span><span class="sxs-lookup"><span data-stu-id="b737e-209">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="b737e-210">В следующей части `makeOneProvidedType` предоставляет метод экземпляра с одним параметром.</span><span class="sxs-lookup"><span data-stu-id="b737e-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="b737e-211">Наконец создайте вложенный тип, содержащий 100 вложенных свойств.</span><span class="sxs-lookup"><span data-stu-id="b737e-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="b737e-212">Создание этого вложенные типа и его свойства задерживается, то есть, вычисляемые по требованию.</span><span class="sxs-lookup"><span data-stu-id="b737e-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="b737e-213">Сведения об удаленных предоставляемых типов</span><span class="sxs-lookup"><span data-stu-id="b737e-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="b737e-214">В примере в этом разделе приводится только *стереть предоставляемых типов*, что особенно полезны в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="b737e-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="b737e-215">При написании поставщика для информационное пространство, который содержит только данные и методы.</span><span class="sxs-lookup"><span data-stu-id="b737e-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="b737e-216">При написании поставщика, где семантику точных типов среды выполнения не являются критическими для практического использования пространства сведения.</span><span class="sxs-lookup"><span data-stu-id="b737e-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="b737e-217">При написании поставщика для информационное пространство, который является слишком большим, соединенных друг с другом, чтобы оно не технически возможно, для создания реальных типов .NET для информации место.</span><span class="sxs-lookup"><span data-stu-id="b737e-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="b737e-218">В этом примере каждый предоставленный тип удаления данных в тип `obj`, и все случаи использования типа будут отображаться как тип `obj` в скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="b737e-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="b737e-219">На самом деле базовых объектов в этих примерах являются строками, но тип будет отображаться как `System.Object` в .NET, скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="b737e-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="b737e-220">Как все случаи использования усилий используется явная упаковка, распаковка-преобразование и приведение к разрушить удалены типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="b737e-221">В этом случае при использовании объекта, может привести приведения исключение, которое является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="b737e-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="b737e-222">Поставщик среды выполнения можно определить собственный тип закрытого представление для защиты от представления значение false.</span><span class="sxs-lookup"><span data-stu-id="b737e-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="b737e-223">Не удается определить удаленных типов в F #.</span><span class="sxs-lookup"><span data-stu-id="b737e-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="b737e-224">Только в том случае, если типы могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="b737e-224">Only provided types may be erased.</span></span> <span data-ttu-id="b737e-225">Необходимо понимать последствия обоих Практическое применение, а семантических одним удаленных типов для поставщика тип или поставщика, который предоставляет удалены типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="b737e-226">Удаленный тип имеет тип не реальными .NET.</span><span class="sxs-lookup"><span data-stu-id="b737e-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="b737e-227">Таким образом точное отражение не поддерживается на тип элемента, и может разрушить удаленных типов при использовании приведений среды выполнения и другие методы, которые используют семантику типа точное время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b737e-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="b737e-228">Subversion удаленных типов часто приводит к исключениям приведения типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b737e-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="b737e-229">Выбор представления для удаления предоставленных типов</span><span class="sxs-lookup"><span data-stu-id="b737e-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="b737e-230">Некоторые варианты использования удаленных предоставляемых типов нет представления не требуется.</span><span class="sxs-lookup"><span data-stu-id="b737e-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="b737e-231">Например удаленный в тип может содержать только статические свойства и члены и нет конструкторов и методов и свойств возвращает экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="b737e-232">Если требуется получить доступ из удаленных экземпляров предоставленного типа, необходимо учитывать следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="b737e-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="b737e-233">**Что такое стирания предоставленного типа**</span><span class="sxs-lookup"><span data-stu-id="b737e-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="b737e-234">Стирания предоставленного типа является, как тип появится в скомпилированном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b737e-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="b737e-235">Стирания предоставленный класс стертой типа является всегда первый не удалены базовым типом в цепочке наследования типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="b737e-236">Всегда является стирания предоставленный интерфейс стертой типа `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="b737e-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="b737e-237">**Что такое представления предоставленного типа**</span><span class="sxs-lookup"><span data-stu-id="b737e-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="b737e-238">Набор возможных объектов для удаленных предоставленного типа, называются его представления.</span><span class="sxs-lookup"><span data-stu-id="b737e-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="b737e-239">В примере в этом документе представления всех удаленных предоставляемых типов `Type1..Type100` всегда являются объектами string.</span><span class="sxs-lookup"><span data-stu-id="b737e-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="b737e-240">Все представления предоставленного типа должны быть совместимы с стирания предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="b737e-241">(В противном случае компилятор F # будет выдавать ошибку для использования поставщика типа, или создается непроверяемый код .NET, который является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="b737e-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="b737e-242">Поставщик типов не является допустимым, если он возвращает код, который дает представление, которое является недопустимым.)</span><span class="sxs-lookup"><span data-stu-id="b737e-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="b737e-243">Можно выбрать представление для указанных объектов с помощью любого из следующих подходов, которые являются очень часто.</span><span class="sxs-lookup"><span data-stu-id="b737e-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="b737e-244">Если просто предоставляет строго типизированной оболочки на существующий тип .NET, часто имеет смысл для типа, чтобы стереть к этому типу, используйте экземпляры этого типа в качестве представления или оба.</span><span class="sxs-lookup"><span data-stu-id="b737e-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="b737e-245">Этот подход используется, когда большинство существующих методов для этого типа по-прежнему имеет смысла при использовании строго типизированную версию.</span><span class="sxs-lookup"><span data-stu-id="b737e-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="b737e-246">Если требуется значительно создать интерфейс API, который отличается от любого существующего API .NET, имеет смысл создать типы среды выполнения, которые будут усилий и представления для указанных типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="b737e-247">В примере в этом документе используются строки как представления указанных объектов.</span><span class="sxs-lookup"><span data-stu-id="b737e-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="b737e-248">Часто возможно, следует использовать для представления других объектов.</span><span class="sxs-lookup"><span data-stu-id="b737e-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="b737e-249">Например вы можете использовать словарь, контейнер свойств:</span><span class="sxs-lookup"><span data-stu-id="b737e-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="b737e-250">Кроме того могут определять тип в поставщике тип, который будет использоваться во время выполнения для формирования представление, вместе с одной или несколькими операциями среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="b737e-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="b737e-251">Предоставляемые элементы затем можно создать экземпляры объектов данного типа:</span><span class="sxs-lookup"><span data-stu-id="b737e-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="b737e-252">В этом случае вы можете (необязательно) использовать этот тип, усилий, указав этот тип как `baseType` при создании `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="b737e-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="b737e-253">Основные результаты</span><span class="sxs-lookup"><span data-stu-id="b737e-253">Key Lessons</span></span>

<span data-ttu-id="b737e-254">В предыдущем разделе описано создание простой стирания поставщик типов, который предоставляет широкий набор типов, свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="b737e-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="b737e-255">В этом разделе также объясняется понятие усилий, включая некоторые преимущества и недостатки предоставляет типы данных, удаленных из поставщика типов и обсуждается представлениями удаленных типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="b737e-256">Тип поставщика, который использует статические параметры</span><span class="sxs-lookup"><span data-stu-id="b737e-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="b737e-257">Возможность параметризовать поставщиков типов, статические данные включает разнообразные сценарии, даже в случаях, когда поставщик не требуется доступ к любым локальным или удаленным данным.</span><span class="sxs-lookup"><span data-stu-id="b737e-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="b737e-258">В этом разделе вы узнаете, как некоторые основные методы совместное размещение такой поставщик.</span><span class="sxs-lookup"><span data-stu-id="b737e-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="b737e-259">Введите проверкой Regex-поставщик</span><span class="sxs-lookup"><span data-stu-id="b737e-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="b737e-260">Предположим, необходимо реализовать тип поставщика по использованию регулярных выражений, являющийся оболочкой для .NET <xref:System.Text.RegularExpressions.Regex> библиотек в интерфейс, который предоставляет следующие гарантии компиляции:</span><span class="sxs-lookup"><span data-stu-id="b737e-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="b737e-261">Проверка, является ли допустимым регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="b737e-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="b737e-262">Предоставление именованных свойств на соответствий, которые основаны на любые имена групп в регулярном выражении.</span><span class="sxs-lookup"><span data-stu-id="b737e-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="b737e-263">В этом разделе показано, как использовать для создания поставщиков типов `RegexTyped` введите параметризует, шаблон регулярного выражения, чтобы предоставить следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="b737e-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="b737e-264">Компилятор выдает ошибку, если указанный шаблон не является допустимым, и поставщик типов можно извлечь группы из шаблона, чтобы вы могли обращаться к ним с помощью свойства совпадает с именем.</span><span class="sxs-lookup"><span data-stu-id="b737e-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="b737e-265">При разработке поставщиков типов, можно как должен выглядеть без поддержки API-интерфейса для конечных пользователей и как преобразует такой подход в коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b737e-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="b737e-266">Приведенный ниже показано, как использовать такие API-Интерфейс для получения компонентов код области:</span><span class="sxs-lookup"><span data-stu-id="b737e-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="b737e-267">В следующем примере показано, как поставщик типа преобразует эти вызовы:</span><span class="sxs-lookup"><span data-stu-id="b737e-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="b737e-268">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="b737e-268">Note the following points:</span></span>

- <span data-ttu-id="b737e-269">Стандартный тип Regex представляет параметризованного `RegexTyped` типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="b737e-270">`RegexTyped` Конструктор приводит к вызову конструктора Regex, передавая статический тип аргумента для шаблона.</span><span class="sxs-lookup"><span data-stu-id="b737e-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="b737e-271">Результаты `Match` метод представлены стандартные <xref:System.Text.RegularExpressions.Match> типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="b737e-272">Каждой именованной группы приведет к предоставляемого свойства и обращение к свойству приводит к использованию индексатора на соответствие `Groups` коллекции.</span><span class="sxs-lookup"><span data-stu-id="b737e-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="b737e-273">В следующем коде показан основной логику для реализации такого поставщика, и в этом примере не включает добавление всех элементов в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="b737e-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="b737e-274">Сведения о каждом добавлен элемент см.</span><span class="sxs-lookup"><span data-stu-id="b737e-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="b737e-275">Полный код, загрузите образец с [F # 3.0 образец пакета](https://fsharp3sample.codeplex.com) на веб-сайте Codeplex.</span><span class="sxs-lookup"><span data-stu-id="b737e-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

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

<span data-ttu-id="b737e-276">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="b737e-276">Note the following points:</span></span>

- <span data-ttu-id="b737e-277">Поставщик типа принимает два параметра статического: `pattern`, который является обязательным и `options`, которой являются необязательными (поскольку предоставляется значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b737e-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="b737e-278">После статических аргументов, можно создать экземпляр регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="b737e-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="b737e-279">Этот экземпляр вызовет исключение, если регулярное выражение имеет неправильный формат, и эта ошибка будет выводиться пользователям.</span><span class="sxs-lookup"><span data-stu-id="b737e-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="b737e-280">В пределах `DefineStaticParameters` обратного вызова, определите тип, который будет возвращаться после аргументов.</span><span class="sxs-lookup"><span data-stu-id="b737e-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="b737e-281">Этот код задает `HideObjectMethods` значение true, чтобы возможности IntelliSense будет по-прежнему упрощенное.</span><span class="sxs-lookup"><span data-stu-id="b737e-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="b737e-282">Этот атрибут вызывает `Equals`, `GetHashCode`, `Finalize`, и `GetType` члены должны быть отключены из списка IntelliSense для предоставленного объекта.</span><span class="sxs-lookup"><span data-stu-id="b737e-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="b737e-283">Вы используете `obj` как базовый тип метода, но вы будете использовать `Regex` объект как представление во время выполнения этого типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b737e-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="b737e-284">Вызов `Regex` конструктор вызывает <xref:System.ArgumentException> при регулярное выражение является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="b737e-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="b737e-285">Компилятор перехватывает это исключение и сообщение об ошибке для пользователя во время компиляции, а также в редакторе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b737e-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="b737e-286">Это исключение позволяет регулярные выражения для проверки без запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b737e-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="b737e-287">Так как она не содержит все значимые методов или свойств типа, определенного выше еще не полезно.</span><span class="sxs-lookup"><span data-stu-id="b737e-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="b737e-288">Сначала добавьте статический `IsMatch` метод:</span><span class="sxs-lookup"><span data-stu-id="b737e-288">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="b737e-289">Предыдущий код определяет метод `IsMatch`, который принимает строку в качестве входных данных и возвращает `bool`.</span><span class="sxs-lookup"><span data-stu-id="b737e-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="b737e-290">Единственной сложностью является использование класса `args` аргумент `InvokeCode` определения.</span><span class="sxs-lookup"><span data-stu-id="b737e-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="b737e-291">В этом примере `args` является список предложений, который представляет аргументы для этого метода.</span><span class="sxs-lookup"><span data-stu-id="b737e-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="b737e-292">Если метод является методом экземпляра, первый аргумент представляет `this` аргумент.</span><span class="sxs-lookup"><span data-stu-id="b737e-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="b737e-293">Однако для статического метода, аргументы — все, что явно заданные аргументы в метод.</span><span class="sxs-lookup"><span data-stu-id="b737e-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="b737e-294">Обратите внимание, соответствие тип значения, заключенные в кавычки указанный тип возвращаемого значения (в данном случае `bool`).</span><span class="sxs-lookup"><span data-stu-id="b737e-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="b737e-295">Также Обратите внимание, что этот код использует `AddXmlDoc` метод, чтобы убедиться в том, что предоставленному методу также имеет полезные документации, доступной через IntelliSense можно указать.</span><span class="sxs-lookup"><span data-stu-id="b737e-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="b737e-296">Добавьте метод Match экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b737e-296">Next, add an instance Match method.</span></span> <span data-ttu-id="b737e-297">Тем не менее, этот метод должен возвращать значение предоставленного `Match` тип, так что группы можно получить доступ к строго типизированным образом.</span><span class="sxs-lookup"><span data-stu-id="b737e-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="b737e-298">Таким образом, сначала объявить `Match` типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="b737e-299">Поскольку этот тип зависит от шаблон, который указан в качестве статического аргумента, этот тип должен быть вложен в определении параметризованного типа:</span><span class="sxs-lookup"><span data-stu-id="b737e-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="b737e-300">Затем добавьте одно свойство в тип соответствия для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="b737e-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="b737e-301">Во время выполнения, соответствие представляется в виде <xref:System.Text.RegularExpressions.Match> значения, поэтому необходимо использовать предложение, которое определяет свойство <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство, чтобы получить соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="b737e-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="b737e-302">Обратите внимание, что вы добавляете XML-документации для указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="b737e-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="b737e-303">Также Обратите внимание, что свойство доступно для чтения, если `GetterCode` предоставляется функции и свойства могут записываться при `SetterCode` функция предоставляется, поэтому результирующее свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b737e-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="b737e-304">Теперь можно создать метод экземпляра, который возвращает значение этого `Match` типа:</span><span class="sxs-lookup"><span data-stu-id="b737e-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="b737e-305">Поскольку создается методом экземпляра `args.[0]` представляет `RegexTyped` экземпляр, на котором вызывается метод, и `args.[1]` является входного аргумента.</span><span class="sxs-lookup"><span data-stu-id="b737e-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="b737e-306">Наконец предоставляет конструктор для создания экземпляров указанного типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="b737e-307">Просто стирает конструктор для создания стандартных экземпляров регулярных выражений .NET упаковывается в объект снова, поскольку `obj` является стирания предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="b737e-308">С данным изменением пример использования API, указанном ранее в этом разделе работает надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="b737e-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="b737e-309">Ниже приведен полный и последнем:</span><span class="sxs-lookup"><span data-stu-id="b737e-309">The following code is complete and final:</span></span>

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
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

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

### <a name="key-lessons"></a><span data-ttu-id="b737e-310">Основные результаты</span><span class="sxs-lookup"><span data-stu-id="b737e-310">Key Lessons</span></span>

<span data-ttu-id="b737e-311">В этом разделе описано создание поставщика типов, который работает на его статических параметров.</span><span class="sxs-lookup"><span data-stu-id="b737e-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="b737e-312">Поставщик проверяет параметр static и предоставляет операции, основанные на его значение.</span><span class="sxs-lookup"><span data-stu-id="b737e-312">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="b737e-313">Поставщик типов, поддерживаемый локальные данные</span><span class="sxs-lookup"><span data-stu-id="b737e-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="b737e-314">Часто можно поставщиков типов для представления API, основываясь на не только статические параметры, но данные из локальных или удаленных систем.</span><span class="sxs-lookup"><span data-stu-id="b737e-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="b737e-315">В этом разделе рассматриваются поставщиков типов, основанных на локальных данных, например локальные файлы данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-315">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="b737e-316">Поставщик простой CSV-файла</span><span class="sxs-lookup"><span data-stu-id="b737e-316">Simple CSV File Provider</span></span>

<span data-ttu-id="b737e-317">В качестве простого примера рассмотрим поставщика типов для доступа к научных данных в формате с разделителями запятыми значения (CSV).</span><span class="sxs-lookup"><span data-stu-id="b737e-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="b737e-318">В этом разделе предполагается, что CSV-файлы содержат строку заголовка, следуют данных с плавающей запятой, как показано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="b737e-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>


|<span data-ttu-id="b737e-319">Расстояние (счетчик)</span><span class="sxs-lookup"><span data-stu-id="b737e-319">Distance (meter)</span></span>|<span data-ttu-id="b737e-320">Время (сек)</span><span class="sxs-lookup"><span data-stu-id="b737e-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="b737e-321">50.0</span><span class="sxs-lookup"><span data-stu-id="b737e-321">50.0</span></span>|<span data-ttu-id="b737e-322">3.7</span><span class="sxs-lookup"><span data-stu-id="b737e-322">3.7</span></span>|
|<span data-ttu-id="b737e-323">100.0</span><span class="sxs-lookup"><span data-stu-id="b737e-323">100.0</span></span>|<span data-ttu-id="b737e-324">5.2</span><span class="sxs-lookup"><span data-stu-id="b737e-324">5.2</span></span>|
|<span data-ttu-id="b737e-325">150.0</span><span class="sxs-lookup"><span data-stu-id="b737e-325">150.0</span></span>|<span data-ttu-id="b737e-326">6.4</span><span class="sxs-lookup"><span data-stu-id="b737e-326">6.4</span></span>|

<span data-ttu-id="b737e-327">В этом разделе показано, как указать тип, который можно использовать для получения строк с `Distance` свойство типа `float<meter>` и `Time` свойство типа `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="b737e-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="b737e-328">Для простоты предполагается следующее:</span><span class="sxs-lookup"><span data-stu-id="b737e-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="b737e-329">Имена заголовков являются либо меньше единицы или иметь формат «Имя (единицы)» и не могут содержать запятые.</span><span class="sxs-lookup"><span data-stu-id="b737e-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="b737e-330">Единицы измерения — это все единицы международной Systeme (SI) как [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames модуль (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) определяется модулем.</span><span class="sxs-lookup"><span data-stu-id="b737e-330">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="b737e-331">Единицы просты (например, контролировать), а не составные (например, индикатор в секунду).</span><span class="sxs-lookup"><span data-stu-id="b737e-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="b737e-332">Все столбцы содержат данных с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="b737e-332">All columns contain floating point data.</span></span>

<span data-ttu-id="b737e-333">Более полный поставщик будет ослабить эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="b737e-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="b737e-334">Снова первым делом следует учитывать, как должен выглядеть интерфейс API.</span><span class="sxs-lookup"><span data-stu-id="b737e-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="b737e-335">Получает `info.csv` файла с содержимым из предыдущей таблицы (в формате с разделителями запятыми), пользователи поставщика должны иметь возможность писать код, аналогичный следующему примеру:</span><span class="sxs-lookup"><span data-stu-id="b737e-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="b737e-336">В этом случае компилятор должен преобразовать эти вызовы в нечто похожее на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="b737e-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="b737e-337">Оптимальной преобразования требуется поставщик типов для определения реальную `CsvFile` типа в сборке поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="b737e-338">Поставщики типов часто используют несколько вспомогательные типы и методы программы-оболочки для важных логических.</span><span class="sxs-lookup"><span data-stu-id="b737e-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="b737e-339">Поскольку меры будут удалены во время выполнения, можно использовать `float[]` как уничтоженные тип строки.</span><span class="sxs-lookup"><span data-stu-id="b737e-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="b737e-340">Как разные измерения типа компилятор будет рассматривать различных столбцов.</span><span class="sxs-lookup"><span data-stu-id="b737e-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="b737e-341">Например, первый столбец в нашем примере имеет тип `float<meter>`, а второй — `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="b737e-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="b737e-342">Однако вместо удаленных представление может оставаться довольно просто.</span><span class="sxs-lookup"><span data-stu-id="b737e-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="b737e-343">В следующем коде показано ядро реализации.</span><span class="sxs-lookup"><span data-stu-id="b737e-343">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

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

<span data-ttu-id="b737e-344">Обратите внимание на следующие аспекты реализации:</span><span class="sxs-lookup"><span data-stu-id="b737e-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="b737e-345">Перегруженные конструкторы позволяют исходный файл или ту, которая имеет идентичные схемы для чтения.</span><span class="sxs-lookup"><span data-stu-id="b737e-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="b737e-346">Этот вариант является стандартным при написании поставщика типа для источников данных на локальном или удаленном, и этот шаблон позволяет локальный файл для использования в качестве шаблона для удаленных данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="b737e-347">Можно использовать [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) значение, которое передается в конструктор поставщика типа для разрешения имен с относительным путем к файлу.</span><span class="sxs-lookup"><span data-stu-id="b737e-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="b737e-348">Можно использовать `AddDefinitionLocation` метод для определения местоположения указанные свойства.</span><span class="sxs-lookup"><span data-stu-id="b737e-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="b737e-349">Таким образом Если вы используете `Go To Definition` предоставленное свойство CSV-файл открывается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b737e-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="b737e-350">Можно использовать `ProvidedMeasureBuilder` типов для поиска SI единицы и создания соответствующего `float<_>` типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="b737e-351">Основные результаты</span><span class="sxs-lookup"><span data-stu-id="b737e-351">Key Lessons</span></span>

<span data-ttu-id="b737e-352">В этом разделе описано создание поставщика типов для локальный источник данных с простой схемой, которая содержится в самого источника данных.</span><span class="sxs-lookup"><span data-stu-id="b737e-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="b737e-353">Если продолжить</span><span class="sxs-lookup"><span data-stu-id="b737e-353">Going Further</span></span>

<span data-ttu-id="b737e-354">В следующих разделах приведены рекомендации для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="b737e-354">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="b737e-355">Рассмотрим скомпилированный код для удаленных типов</span><span class="sxs-lookup"><span data-stu-id="b737e-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="b737e-356">Чтобы получить представление об как использование поставщика типов соответствует коду, который создается, рассмотрим следующую функцию с помощью `HelloWorldTypeProvider` , используемый этой статьи.</span><span class="sxs-lookup"><span data-stu-id="b737e-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="b737e-357">Ниже приведен результирующий код, с помощью ildasm.exe decompiled изображения.</span><span class="sxs-lookup"><span data-stu-id="b737e-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
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

<span data-ttu-id="b737e-358">Как показано в примере, все упоминания типа `Type1` и `InstanceProperty` удалены свойство, оставляя участвующих только операции с типами среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b737e-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="b737e-359">Проектирование и соглашения об именовании для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="b737e-359">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="b737e-360">Соблюдайте следующие соглашения для создания поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="b737e-361">**Поставщики для подключения к протоколов** в общем случае имена большинства DLL-библиотеки поставщика для протоколов подключения данных и служб, например соединения OData или SQL, должна завершиться в `TypeProvider` или `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="b737e-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="b737e-362">Например используйте имя библиотеки DLL, примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="b737e-362">For example, use a DLL name that resembles the following string:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.dll
```

<span data-ttu-id="b737e-363">Убедитесь, что ваш предоставляемых типов являются членами соответствующее пространство имен и указать протокол связи, реализованной:</span><span class="sxs-lookup"><span data-stu-id="b737e-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="b737e-364">**Поставщики служебной программы для кодирования Общие**.</span><span class="sxs-lookup"><span data-stu-id="b737e-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="b737e-365">Для программы поставщика типов, например для регулярных выражений поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b737e-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="b737e-366">В этом случае предоставленный тип будет выглядеть в соответствующий момент согласно обычным соглашения разработки .NET:</span><span class="sxs-lookup"><span data-stu-id="b737e-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="b737e-367">**Источники данных одноэлементный**.</span><span class="sxs-lookup"><span data-stu-id="b737e-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="b737e-368">Некоторые поставщики типов подключения для одного выделенного источника данных и для предоставления только данные.</span><span class="sxs-lookup"><span data-stu-id="b737e-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="b737e-369">В этом случае следует удалить `TypeProvider` суффикс и используйте обычный соглашения для .NET:</span><span class="sxs-lookup"><span data-stu-id="b737e-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="b737e-370">Дополнительные сведения см. в разделе `GetConnection` разработать соглашение, которое описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b737e-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="b737e-371">Шаблоны разработки для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="b737e-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="b737e-372">В следующих разделах описаны принципы разработки, которые можно использовать при разработке поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-372">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="b737e-373">Шаблон разработки GetConnection</span><span class="sxs-lookup"><span data-stu-id="b737e-373">The GetConnection Design Pattern</span></span>
<span data-ttu-id="b737e-374">Большинство поставщиков типов должны быть написаны для использования `GetConnection` шаблон, используемый поставщиками типов в FSharp.Data.TypeProviders.dll, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b737e-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="b737e-375">Поставщики типов удаленных данных и служб</span><span class="sxs-lookup"><span data-stu-id="b737e-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="b737e-376">Прежде чем создать поставщик типов, который содержится в удаленных данных и служб, необходимо учитывать ряд проблем, которые принадлежат подключенных программирования.</span><span class="sxs-lookup"><span data-stu-id="b737e-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="b737e-377">Эти проблемы включают следующее:</span><span class="sxs-lookup"><span data-stu-id="b737e-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="b737e-378">Сопоставление схем</span><span class="sxs-lookup"><span data-stu-id="b737e-378">schema mapping</span></span>

- <span data-ttu-id="b737e-379">liveness и недействительности при наличии изменений схемы</span><span class="sxs-lookup"><span data-stu-id="b737e-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="b737e-380">Кэширование схем</span><span class="sxs-lookup"><span data-stu-id="b737e-380">schema caching</span></span>

- <span data-ttu-id="b737e-381">реализации асинхронных операций доступа к данным</span><span class="sxs-lookup"><span data-stu-id="b737e-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="b737e-382">Поддержка запросов, включая запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="b737e-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="b737e-383">учетные данные и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b737e-383">credentials and authentication</span></span>

<span data-ttu-id="b737e-384">В этом разделе не исследовать эти дополнительные проблемы.</span><span class="sxs-lookup"><span data-stu-id="b737e-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="b737e-385">Дополнительные методы разработки</span><span class="sxs-lookup"><span data-stu-id="b737e-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="b737e-386">При написании собственных поставщиков типов, можно использовать следующие дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="b737e-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="b737e-387">Создание типов и членов по требованию</span><span class="sxs-lookup"><span data-stu-id="b737e-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="b737e-388">ProvidedType API откладывала версий AddMember.</span><span class="sxs-lookup"><span data-stu-id="b737e-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="b737e-389">Эти версии используются для создания пространства по требованию типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="b737e-390">Массив типов и экземпляров универсального типа</span><span class="sxs-lookup"><span data-stu-id="b737e-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="b737e-391">Сделать указанных членов, (, подписи включают типы массивов, типы byref и создание экземпляров универсальных типов) с помощью нормали `MakeArrayType`, `MakePointerType`, и `MakeGenericType` на любом экземпляре <xref:System.Type>, в том числе `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="b737e-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="b737e-392">В некоторых случаях может потребоваться использовать его в `ProvidedTypeBuilder.MakeGenericType`.</span><span class="sxs-lookup"><span data-stu-id="b737e-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="b737e-393">В разделе [документации по пакету SDK поставщика типа](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="b737e-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="b737e-394">Предоставление единицы измерения заметок</span><span class="sxs-lookup"><span data-stu-id="b737e-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="b737e-395">ProvidedTypes API предоставляет вспомогательные методы для предоставления мер заметок.</span><span class="sxs-lookup"><span data-stu-id="b737e-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="b737e-396">Например, чтобы указать тип `float<kg>`, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="b737e-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="b737e-397">Чтобы указать тип `Nullable<decimal<kg/m^2>>`, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="b737e-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="b737e-398">Доступ к ресурсам локального проекта или локальными для сценария</span><span class="sxs-lookup"><span data-stu-id="b737e-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="b737e-399">Каждый экземпляр поставщика типа может быть задан `TypeProviderConfig` значение во время построения.</span><span class="sxs-lookup"><span data-stu-id="b737e-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="b737e-400">Это значение содержит «разрешения папки» для поставщика (то есть папка проекта для компиляции или каталог, содержащий сценарий), список сборок, на которые имеются ссылки и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="b737e-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="b737e-401">Недействительность</span><span class="sxs-lookup"><span data-stu-id="b737e-401">Invalidation</span></span>

<span data-ttu-id="b737e-402">Поставщики могут вызывать сигналы о недействительности уведомить службу F #, которые могли изменить предположения схемы.</span><span class="sxs-lookup"><span data-stu-id="b737e-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="b737e-403">При возникновении недействительности typecheck Повторено, если поставщик находится в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b737e-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="b737e-404">Этот сигнал будет игнорироваться, если поставщик размещается в F # Interactive или компилятором F # (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="b737e-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="b737e-405">Кэширование сведений о схеме</span><span class="sxs-lookup"><span data-stu-id="b737e-405">Caching Schema Information</span></span>

<span data-ttu-id="b737e-406">Поставщики часто необходимо кэшировать доступ к сведениям о схеме.</span><span class="sxs-lookup"><span data-stu-id="b737e-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="b737e-407">Кэшированные данные должны храниться с помощью имени файла, которое задано как статического параметра или пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="b737e-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="b737e-408">Кэширование схем является примером `LocalSchemaFile` параметра в тип поставщики `FSharp.Data.TypeProviders` сборки.</span><span class="sxs-lookup"><span data-stu-id="b737e-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="b737e-409">В реализации этих поставщиков этот параметр статических направляет поставщик типов, чтобы использовать сведения о схеме в указанный локальный файл вместо обращения к источнику данных по сети.</span><span class="sxs-lookup"><span data-stu-id="b737e-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="b737e-410">Для использования кэшированных сведений о схеме, необходимо задать параметр static `ForceUpdate` для `false`.</span><span class="sxs-lookup"><span data-stu-id="b737e-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="b737e-411">Подобный прием можно использовать для доступа к данным и отключенные от сети.</span><span class="sxs-lookup"><span data-stu-id="b737e-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="b737e-412">Резервное копирование сборки</span><span class="sxs-lookup"><span data-stu-id="b737e-412">Backing Assembly</span></span>

<span data-ttu-id="b737e-413">При компиляции `.dll` или `.exe` -файле, резервное копирование DLL-файла для создаваемых типов статически связанная с результирующей сборки.</span><span class="sxs-lookup"><span data-stu-id="b737e-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="b737e-414">Эта ссылка создается путем копирования определения типов промежуточного языка (IL) и все управляемые ресурсы из сборки резервное копирование в окончательную сборку.</span><span class="sxs-lookup"><span data-stu-id="b737e-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="b737e-415">При использовании F # Interactive, резервное копирование DLL-файл не копируется и вместо него загружается непосредственно в F # Interactive процесса.</span><span class="sxs-lookup"><span data-stu-id="b737e-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="b737e-416">Исключения и диагностику из поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="b737e-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="b737e-417">Все случаи использования все элементы из предоставляемых типов могут вызывать исключения.</span><span class="sxs-lookup"><span data-stu-id="b737e-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="b737e-418">Во всех случаях если поставщик типа вызывает исключение, компилятор узла атрибутов ошибки поставщику определенного типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="b737e-419">Тип поставщика исключения никогда не должны появиться внутренних ошибок компилятора.</span><span class="sxs-lookup"><span data-stu-id="b737e-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="b737e-420">Поставщики типов не может сообщить предупреждения.</span><span class="sxs-lookup"><span data-stu-id="b737e-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="b737e-421">Поставщик типа размещается в компиляторе F # среды разработки F # и F # Interactive, перехватывает все исключения из этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="b737e-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="b737e-422">Свойство сообщения всегда является текст ошибки, и отображается не трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="b737e-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="b737e-423">Если исключение, можно вызывать следующие примеры: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="b737e-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="b737e-424">Предоставляя типы, созданные</span><span class="sxs-lookup"><span data-stu-id="b737e-424">Providing Generated Types</span></span>

<span data-ttu-id="b737e-425">На данный момент в настоящем документе содержатся предоставление удаленных типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="b737e-426">Также можно использовать механизм поставщика типов в языке F # для предоставления созданных типов, которые добавляются в виде реального определений типов .NET в программу пользователей.</span><span class="sxs-lookup"><span data-stu-id="b737e-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="b737e-427">Вы должны ссылаться на созданный типы, предоставляемые с помощью определения типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="b737e-428">0,2 ProvidedTypes вспомогательный код, который является частью версии F # 3.0 имеется только ограниченная поддержка для предоставления создаваемых типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="b737e-429">Для определения создаваемого типа должны выполняться следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="b737e-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="b737e-430">`isErased` должно быть присвоено `false`.</span><span class="sxs-lookup"><span data-stu-id="b737e-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="b737e-431">Созданного типа должны добавляться к вновь созданной `ProvidedAssembly()`, который представляет контейнер для созданного кода фрагментов.</span><span class="sxs-lookup"><span data-stu-id="b737e-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="b737e-432">Поставщик должен иметь сборку, которая содержит фактические резервного .NET DLL-файл, соответствующий файл DLL-файл на диске.</span><span class="sxs-lookup"><span data-stu-id="b737e-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="b737e-433">Правила и ограничения</span><span class="sxs-lookup"><span data-stu-id="b737e-433">Rules and Limitations</span></span>

<span data-ttu-id="b737e-434">При написании поставщиков типов, примите во внимание следующие правила и ограничения.</span><span class="sxs-lookup"><span data-stu-id="b737e-434">When you write type providers, keep the following rules and limitations in mind.</span></span>


### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="b737e-435">Предоставляемых типов должен быть доступен</span><span class="sxs-lookup"><span data-stu-id="b737e-435">Provided types must be reachable</span></span>

<span data-ttu-id="b737e-436">Все входящие типы должны быть доступны из типов-nested.</span><span class="sxs-lookup"><span data-stu-id="b737e-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="b737e-437">Типы, не являющегося вложенным, получают в вызове `TypeProviderForNamespaces` конструктор или вызов `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="b737e-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="b737e-438">Например, если поставщик предоставляет тип `StaticClass.P : T`, необходимо убедиться в том, что T невложенном типе или вложенными в один.</span><span class="sxs-lookup"><span data-stu-id="b737e-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="b737e-439">Например, некоторые поставщики иметь статического класса, такие как `DataTypes` , содержащие такие `T1, T2, T3, ...` типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="b737e-440">В противном случае ошибка сообщает, что была обнаружена ссылка на тип "T" в сборке A, но не удалось найти тип в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="b737e-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="b737e-441">При появлении этой ошибки, убедитесь, что все подтипы можно получить от поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="b737e-442">Примечание: Эти `T1, T2, T3...` типы называются *на лету* типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="b737e-443">Не забудьте поместить их в доступного пространства имен или родительского типа.</span><span class="sxs-lookup"><span data-stu-id="b737e-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="b737e-444">Ограничения типа механизма поставщика</span><span class="sxs-lookup"><span data-stu-id="b737e-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="b737e-445">Механизм поставщика типов в языке F # имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="b737e-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="b737e-446">Базовой инфраструктуры для поставщиков типов F # не поддерживает универсальные типы или универсальные методы.</span><span class="sxs-lookup"><span data-stu-id="b737e-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="b737e-447">Механизм не поддерживает вложенные типы с указанием статических параметров.</span><span class="sxs-lookup"><span data-stu-id="b737e-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="b737e-448">Советы по разработке</span><span class="sxs-lookup"><span data-stu-id="b737e-448">Development Tips</span></span>

<span data-ttu-id="b737e-449">Следующие советы могут оказаться полезными в процессе разработки.</span><span class="sxs-lookup"><span data-stu-id="b737e-449">You might find the following tips helpful during the development process.</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="b737e-450">Запустите два экземпляра Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b737e-450">Run Two Instances of Visual Studio</span></span>

<span data-ttu-id="b737e-451">Можно разрабатывать в одном экземпляре типа поставщика и проверки поставщика в другом, поскольку интегрированная среда разработки тест будет иметь блокировку на DLL-файл, предотвращает перестраивает поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="b737e-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="b737e-452">Таким образом необходимо закрыть второй экземпляр Visual Studio, пока поставщик встроен в первом экземпляре, а затем необходимо повторно открыть второй экземпляр после построения поставщика.</span><span class="sxs-lookup"><span data-stu-id="b737e-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="b737e-453">Отладка с помощью вызовов fsc.exe поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="b737e-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="b737e-454">Поставщики типов можно вызвать с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="b737e-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="b737e-455">fsc.exe (компилятор командной строки F #)</span><span class="sxs-lookup"><span data-stu-id="b737e-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="b737e-456">fsi.exe (F # Interactive компилятор)</span><span class="sxs-lookup"><span data-stu-id="b737e-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="b737e-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="b737e-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="b737e-458">Поставщики типов часто можно отлаживать проще всего с помощью fsc.exe на файл скрипта теста (например, файл script.fsx).</span><span class="sxs-lookup"><span data-stu-id="b737e-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="b737e-459">Вы можете запустить отладчик из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b737e-459">You can launch a debugger from a command prompt.</span></span>

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="b737e-460">Можно использовать ведение журнала печать в stdout.</span><span class="sxs-lookup"><span data-stu-id="b737e-460">You can use print-to-stdout logging.</span></span>


## <a name="see-also"></a><span data-ttu-id="b737e-461">См. также</span><span class="sxs-lookup"><span data-stu-id="b737e-461">See Also</span></span>

* [<span data-ttu-id="b737e-462">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="b737e-462">Type Providers</span></span>](index.md)

* [<span data-ttu-id="b737e-463">Тип поставщика пакета SDK</span><span class="sxs-lookup"><span data-stu-id="b737e-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)

