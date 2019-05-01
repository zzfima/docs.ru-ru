---
title: Учебник. Создание поставщика типов
description: Узнайте, как создать свое собственное F# введите поставщиков в F# 3.0 с помощью проверки несколько поставщиков простого типа, чтобы продемонстрировать основные понятия.
ms.date: 02/02/2019
ms.openlocfilehash: 14e3035d03438aaaa2f6e64210f99e1f149db274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982622"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="0205b-103">Учебник. Создание поставщика типов</span><span class="sxs-lookup"><span data-stu-id="0205b-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="0205b-104">Механизм поставщика типа в F# имеет значительную часть поддержка возможности программирования сведения.</span><span class="sxs-lookup"><span data-stu-id="0205b-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="0205b-105">Этом руководстве описывается создание собственных поставщиков типов посредством разработки из нескольких поставщиков простого типа, чтобы продемонстрировать основные понятия.</span><span class="sxs-lookup"><span data-stu-id="0205b-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="0205b-106">Дополнительные сведения о механизме тип поставщика в F#, см. в разделе [поставщиков типов](index.md).</span><span class="sxs-lookup"><span data-stu-id="0205b-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="0205b-107">F# Экосистемы содержит широкий набор поставщиков типов для часто используемых Интернет и enterprise data services.</span><span class="sxs-lookup"><span data-stu-id="0205b-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="0205b-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="0205b-108">For example:</span></span>

- <span data-ttu-id="0205b-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) включает поставщиков типов для форматы документов JSON, XML, CSV и HTML.</span><span class="sxs-lookup"><span data-stu-id="0205b-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="0205b-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) предоставляет строго типизированный доступ к базам данных SQL через сопоставление объектов и F# запросы LINQ к источникам данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="0205b-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) набор поставщиков типов для компиляции проверен внедрение T-SQL в F#.</span><span class="sxs-lookup"><span data-stu-id="0205b-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="0205b-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) — старые набор поставщиков типов для использования только с программированием для платформы .NET Framework для доступа к службам данных SQL, Entity Framework, OData и WSDL.</span><span class="sxs-lookup"><span data-stu-id="0205b-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="0205b-113">При необходимости, можно создать пользовательские поставщики типов, или вы можете ссылаться на поставщиков типов, созданных другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="0205b-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="0205b-114">Например ваша организация может иметь службу данных, которая предоставляет большого и постоянно растущего ряд именованных наборов данных, каждый из которых свой собственный стабильная схема данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="0205b-115">Можно создать поставщик типов, который считывает схемы и представляет текущее наборов данных на программиста в строго типизированным способом.</span><span class="sxs-lookup"><span data-stu-id="0205b-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0205b-116">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="0205b-116">Before You Start</span></span>

<span data-ttu-id="0205b-117">Механизм поставщика типа в основном предназначен для добавления неизменных данных и службы информационных пространств в F# опыт программирования.</span><span class="sxs-lookup"><span data-stu-id="0205b-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="0205b-118">Этот механизм не поддерживает внедрение информационных пространств, схема которой изменяется во время выполнения программы, одним из способов, которые подходят для логики программы.</span><span class="sxs-lookup"><span data-stu-id="0205b-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="0205b-119">Кроме того механизм не поддерживает intra межъязыкового метапрограммирования, несмотря на то, что этот домен содержит некоторые допустимые варианты использования.</span><span class="sxs-lookup"><span data-stu-id="0205b-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="0205b-120">Этот механизм следует использовать только в том случае, если необходимо, и где разработки поставщик типа выдает очень большое значение.</span><span class="sxs-lookup"><span data-stu-id="0205b-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="0205b-121">Старайтесь не писать поставщик типа, где схема недоступна.</span><span class="sxs-lookup"><span data-stu-id="0205b-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="0205b-122">Аналогично, старайтесь не писать поставщик типа там, где обычный (или даже существующего) было бы достаточно библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="0205b-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="0205b-123">Прежде чем начать, можно задать следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="0205b-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="0205b-124">У вас есть схемы для источника сведения?</span><span class="sxs-lookup"><span data-stu-id="0205b-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="0205b-125">Если таким образом, что такое сопоставление в F# и системе типов .NET?</span><span class="sxs-lookup"><span data-stu-id="0205b-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="0205b-126">Можно использовать интерфейс API (динамической типизацией) в качестве отправной точки для реализации?</span><span class="sxs-lookup"><span data-stu-id="0205b-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="0205b-127">Вам и вашей организации будет недостаточно использует поставщик типов для облегчения написания его оправданной?</span><span class="sxs-lookup"><span data-stu-id="0205b-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="0205b-128">Обычной библиотеки .NET удовлетворят потребности?</span><span class="sxs-lookup"><span data-stu-id="0205b-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="0205b-129">Насколько изменится схемы?</span><span class="sxs-lookup"><span data-stu-id="0205b-129">How much will your schema change?</span></span>

- <span data-ttu-id="0205b-130">Изменится во время кодирования?</span><span class="sxs-lookup"><span data-stu-id="0205b-130">Will it change during coding?</span></span>

- <span data-ttu-id="0205b-131">Изменится между семинары по программированию?</span><span class="sxs-lookup"><span data-stu-id="0205b-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="0205b-132">Изменится во время выполнения программы?</span><span class="sxs-lookup"><span data-stu-id="0205b-132">Will it change during program execution?</span></span>

<span data-ttu-id="0205b-133">Поставщики типов являются наилучшим образом подходит для ситуаций, где схема стабильна, во время выполнения и в течение времени существования скомпилированного кода.</span><span class="sxs-lookup"><span data-stu-id="0205b-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="0205b-134">Поставщик простой тип</span><span class="sxs-lookup"><span data-stu-id="0205b-134">A Simple Type Provider</span></span>

<span data-ttu-id="0205b-135">Этот пример представляет Samples.HelloWorldTypeProvider, аналогичную в примерах `examples` каталог [ F# тип поставщика SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="0205b-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="0205b-136">Поставщик делает доступными «тип space», содержащий 100 удаленных типов, как показано в следующем коде с помощью F# синтаксис подпись и пропуск сведения для всех, кроме `Type1`.</span><span class="sxs-lookup"><span data-stu-id="0205b-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="0205b-137">Дополнительные сведения об удаленных типах см. в разделе [сведения о удалены предоставляемые типы](#details-about-erased-provided-types) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0205b-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

<span data-ttu-id="0205b-138">Обратите внимание на то, что статически известен набор типов и членов, которые предоставляются.</span><span class="sxs-lookup"><span data-stu-id="0205b-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="0205b-139">В этом примере не использовать возможности поставщиков для предоставления типов, которые зависят от схемы.</span><span class="sxs-lookup"><span data-stu-id="0205b-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="0205b-140">Реализация поставщика типов описан в следующем коде, и подробности этого охвачены в следующих разделах этой статьи.</span><span class="sxs-lookup"><span data-stu-id="0205b-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="0205b-141">Возможно, различия между этим кодом и примеров в сети.</span><span class="sxs-lookup"><span data-stu-id="0205b-141">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="0205b-142">Чтобы использовать этот поставщик, откройте отдельный экземпляр Visual Studio и создайте F# скрипта, а затем добавьте ссылку на службу из скрипта с помощью #r, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="0205b-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="0205b-143">Проверьте типы в разделе `Samples.HelloWorldTypeProvider` пространства имен, вызвавшего поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="0205b-144">Перед перекомпиляцией поставщика, убедитесь, что вы уже закрыли все экземпляры Visual Studio и F# интерактивное окно, в которых используется DLL-Библиотека поставщика.</span><span class="sxs-lookup"><span data-stu-id="0205b-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="0205b-145">В противном случае ошибка сборки произойдет, так как выходной библиотеке DLL будет заблокирована.</span><span class="sxs-lookup"><span data-stu-id="0205b-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="0205b-146">Чтобы отладить этот поставщик с помощью выражения print, создание сценария, указывающий на проблему с поставщиком и затем используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0205b-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="0205b-147">Чтобы отладить этот поставщик с помощью Visual Studio, откройте командную строку разработчика для Visual Studio от имени администратора и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0205b-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="0205b-148">Кроме того, откройте Visual Studio откройте меню "Отладка", выберите `Debug/Attach to process…`и подключить к другой `devenv` процесса, где вы редактируете скрипта.</span><span class="sxs-lookup"><span data-stu-id="0205b-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="0205b-149">С помощью этого метода, можно точнее указывать определенной логики у поставщика типов, введя интерактивно выражения в второй экземпляр (с полной поддержкой IntelliSense и других функций).</span><span class="sxs-lookup"><span data-stu-id="0205b-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="0205b-150">Можно отключить только мой код отладки, чтобы выявить ошибки в сформированном коде.</span><span class="sxs-lookup"><span data-stu-id="0205b-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="0205b-151">Сведения о том, как включить или отключить эту функцию, см. в разделе [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="0205b-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="0205b-152">Кроме того, можно также задать исключения первого шанса, перехват, открыв `Debug` меню и выбрав `Exceptions` или нажав клавиши Ctrl + Alt + E, чтобы открыть `Exceptions` диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="0205b-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="0205b-153">В этом диалоговом окне в разделе `Common Language Runtime Exceptions`выберите `Thrown` "флажок".</span><span class="sxs-lookup"><span data-stu-id="0205b-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="0205b-154">Реализация поставщика типов</span><span class="sxs-lookup"><span data-stu-id="0205b-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="0205b-155">В этом разделе пошагово части реализации поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="0205b-156">Во-первых вы определите тип поставщика пользовательского типа самой:</span><span class="sxs-lookup"><span data-stu-id="0205b-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="0205b-157">Этот тип должен быть открытым и должен отметить его атрибутом [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) таким образом, чтобы компилятор распознает поставщика типов при отдельном F# проект ссылается на сборку, содержащую тип.</span><span class="sxs-lookup"><span data-stu-id="0205b-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="0205b-158">*Config* параметр является необязательным и, при его наличии, содержит сведения о конфигурации контекстные экземпляра поставщика типов, F# компилятор создает.</span><span class="sxs-lookup"><span data-stu-id="0205b-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="0205b-159">Далее необходимо реализовать [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0205b-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="0205b-160">В этом случае используется `TypeProviderForNamespaces` тип из `ProvidedTypes` API в качестве базового типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="0205b-161">Этот вспомогательный тип можно заранее предоставить конечную коллекцию, предоставляется пространства имен, непосредственно каждый из которых содержит конечное количество исправлена, заранее типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="0205b-162">В этом контексте, поставщик *заранее* создает типы, даже если они не требуется или не используется.</span><span class="sxs-lookup"><span data-stu-id="0205b-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="0205b-163">Определение локальной частной значения, которые определяют пространство имен для существующих затем найти саму сборку поставщика типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="0205b-164">Эта сборка используется как логический родительский тип удаленных типов, которые предоставляются для более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0205b-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="0205b-165">Создайте функцию для предоставления каждого из типов Type1... Type100.</span><span class="sxs-lookup"><span data-stu-id="0205b-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="0205b-166">Эта функция является более подробно далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0205b-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="0205b-167">Далее создайте 100 указанными типами:</span><span class="sxs-lookup"><span data-stu-id="0205b-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="0205b-168">Добавьте типы как указанное пространство имен:</span><span class="sxs-lookup"><span data-stu-id="0205b-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="0205b-169">Наконец добавьте атрибут сборки, которое указывает, что вы создаете поставщик типа библиотеки DLL:</span><span class="sxs-lookup"><span data-stu-id="0205b-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="0205b-170">Предоставление одного типа и его членов</span><span class="sxs-lookup"><span data-stu-id="0205b-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="0205b-171">`makeOneProvidedType` Функция не работает один из типов предоставления.</span><span class="sxs-lookup"><span data-stu-id="0205b-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="0205b-172">На этом шаге описывается реализация этой функции.</span><span class="sxs-lookup"><span data-stu-id="0205b-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="0205b-173">Во-первых, создайте предоставленный тип (например, тип 1, когда n = 1 или Type57, когда n = 57).</span><span class="sxs-lookup"><span data-stu-id="0205b-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="0205b-174">Следует отметить следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="0205b-174">You should note the following points:</span></span>

- <span data-ttu-id="0205b-175">Это, если тип удаляется.</span><span class="sxs-lookup"><span data-stu-id="0205b-175">This provided type is erased.</span></span>  <span data-ttu-id="0205b-176">Так как можно указать, что базовый тип является `obj`, экземпляров будет отображаться в виде значения типа [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) в скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="0205b-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="0205b-177">При указании типа, невложенными, необходимо указать сборку и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="0205b-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="0205b-178">Для удаленных типов сборка должна быть самой сборки типа поставщика.</span><span class="sxs-lookup"><span data-stu-id="0205b-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="0205b-179">Добавьте XML-документации к типу.</span><span class="sxs-lookup"><span data-stu-id="0205b-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="0205b-180">Эта документация задерживается, то есть, вычисляется по запросу, если компилятор узла должен его.</span><span class="sxs-lookup"><span data-stu-id="0205b-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="0205b-181">Затем следует добавить указанный статическое свойство типа:</span><span class="sxs-lookup"><span data-stu-id="0205b-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="0205b-182">При получении этого свойства всегда будет оцениваться как строка «Hello!».</span><span class="sxs-lookup"><span data-stu-id="0205b-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="0205b-183">`GetterCode` Свойство использует F# предложение, которое представляет код, который создает компилятор узла для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="0205b-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="0205b-184">Дополнительные сведения о предложениях см. в разделе [Цитирование кода (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="0205b-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="0205b-185">Добавьте XML-документации к свойству.</span><span class="sxs-lookup"><span data-stu-id="0205b-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="0205b-186">Теперь подключите указанного свойства в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="0205b-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="0205b-187">Указанный член необходимо присоединить к только один тип.</span><span class="sxs-lookup"><span data-stu-id="0205b-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="0205b-188">В противном случае член никогда не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="0205b-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="0205b-189">Теперь создайте предоставленный конструктор, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="0205b-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="0205b-190">`InvokeCode` Для завершения работы конструктор возвращает F# предложение, которое представляет код, который создает компилятор узла, при вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="0205b-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="0205b-191">Например можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="0205b-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="0205b-192">Экземпляр указанного типа создается с базовыми данными «Данные объекта».</span><span class="sxs-lookup"><span data-stu-id="0205b-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="0205b-193">Заключенные в кавычки кода включает в себя преобразование [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) поскольку этот тип стирания это обеспечило тип (как вы указали при объявлении предоставленного типа).</span><span class="sxs-lookup"><span data-stu-id="0205b-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="0205b-194">Добавьте XML-документации в конструктор и добавьте в предоставленный тип предоставленного конструктора:</span><span class="sxs-lookup"><span data-stu-id="0205b-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="0205b-195">Создайте второй предоставленный конструктор, принимающий один параметр:</span><span class="sxs-lookup"><span data-stu-id="0205b-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="0205b-196">`InvokeCode` Для конструктора снова возвращает F# предложение, которое представляет код, созданный в компиляторе базовой для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="0205b-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="0205b-197">Например можно использовать следующий конструктор:</span><span class="sxs-lookup"><span data-stu-id="0205b-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="0205b-198">Экземпляр указанного типа создается с базовыми данными «10».</span><span class="sxs-lookup"><span data-stu-id="0205b-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="0205b-199">Вы уже могли заметить, `InvokeCode` функция возвращает предложения.</span><span class="sxs-lookup"><span data-stu-id="0205b-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="0205b-200">Входные данные для этой функции — это список выражений, по одному на параметра конструктора.</span><span class="sxs-lookup"><span data-stu-id="0205b-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="0205b-201">В этом случае выражение, которое представляет одно значение параметра доступно в `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="0205b-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="0205b-202">Код для вызова конструктора приводит возвращаемое значение к типу удаленных `obj`.</span><span class="sxs-lookup"><span data-stu-id="0205b-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="0205b-203">После добавления второй конструктор указанного типа, можно создать свойство предоставленный экземпляр:</span><span class="sxs-lookup"><span data-stu-id="0205b-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="0205b-204">При получении данного свойства возвращается длина строки, который является объектом представления.</span><span class="sxs-lookup"><span data-stu-id="0205b-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="0205b-205">`GetterCode` Возвращает F# предложение, которое указывает код, который создает компилятор узла для получения свойства.</span><span class="sxs-lookup"><span data-stu-id="0205b-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="0205b-206">Как и `InvokeCode`, `GetterCode` функция возвращает предложения.</span><span class="sxs-lookup"><span data-stu-id="0205b-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="0205b-207">В компиляторе базовой вызывает эту функцию с помощью списка аргументов.</span><span class="sxs-lookup"><span data-stu-id="0205b-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="0205b-208">В этом случае аргументы включают только одно выражение, представляющее экземпляр, на котором вызывается метод получения значения, к которому можно получить с помощью `args.[0]`. Реализация `GetterCode` затем получает эту предложениям результат в удаленных введите `obj`, и использовать приведение типов для удовлетворения компилятора механизм для проверки типов, что объект представляет собой строку.</span><span class="sxs-lookup"><span data-stu-id="0205b-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="0205b-209">В следующей части `makeOneProvidedType` предоставляет метод экземпляра с одним параметром.</span><span class="sxs-lookup"><span data-stu-id="0205b-209">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="0205b-210">Наконец создайте вложенный тип, содержащий 100 вложенных свойств.</span><span class="sxs-lookup"><span data-stu-id="0205b-210">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="0205b-211">Создание это вложенные типа и его свойства откладывается, то есть, вычисляется по запросу.</span><span class="sxs-lookup"><span data-stu-id="0205b-211">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

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

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="0205b-212">Дополнительные сведения о типах удаленных предоставленный</span><span class="sxs-lookup"><span data-stu-id="0205b-212">Details about Erased Provided Types</span></span>

<span data-ttu-id="0205b-213">В примере в этом разделе приводятся только *удалены указанные типы*, которая особенно полезны в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="0205b-213">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="0205b-214">При написании поставщика для информационное пространство, который содержит только данные и методы.</span><span class="sxs-lookup"><span data-stu-id="0205b-214">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="0205b-215">При написании поставщика, где семантику точных типов среды выполнения не являются критически важными для практического использования информационное пространство.</span><span class="sxs-lookup"><span data-stu-id="0205b-215">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="0205b-216">При написании поставщика для информационное пространство, который является слишком большим, взаимосвязанных, что это не технически возможно, для создания реальных типов .NET для, информационное пространство.</span><span class="sxs-lookup"><span data-stu-id="0205b-216">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="0205b-217">В этом примере каждый предоставленный тип удаляется, чтобы ввести `obj`, и все случаи использования тип отображается как тип `obj` в скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="0205b-217">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="0205b-218">На самом деле, базовых объектов в этих примерах являются строками, но тип будет отображаться как `System.Object` в .NET, скомпилированного кода.</span><span class="sxs-lookup"><span data-stu-id="0205b-218">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="0205b-219">Как и с все случаи использования стирания типа явная упаковка, распаковка-преобразование и приведение к увенчается успехом удалены типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-219">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="0205b-220">В этом случае исключение приведения, которое является недопустимой, может привести к при использовании объекта.</span><span class="sxs-lookup"><span data-stu-id="0205b-220">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="0205b-221">Поставщик среды выполнения можно определить свой собственный тип частного представления для защиты от false представления.</span><span class="sxs-lookup"><span data-stu-id="0205b-221">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="0205b-222">Невозможно определить удаленных типов в F# сам.</span><span class="sxs-lookup"><span data-stu-id="0205b-222">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="0205b-223">Только в том случае, если типы могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="0205b-223">Only provided types may be erased.</span></span> <span data-ttu-id="0205b-224">Необходимо понимать последствия, оба practical и семантике, с помощью удаленных типов для поставщика тип или поставщик, который предоставляет удалены типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-224">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="0205b-225">Удаленный тип не имеет реальной .NET типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-225">An erased type has no real .NET type.</span></span> <span data-ttu-id="0205b-226">Таким образом невозможно выполнить точное отражение на тип, и может подвергнуть опасности удаленных типов при использовании приведений среды выполнения и другие технологии, использующие семантику типа точное время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0205b-226">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="0205b-227">Subversion удаленных типов часто приводит к исключениям приведения типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0205b-227">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="0205b-228">Выбор представления, для удаления предоставляемые типы</span><span class="sxs-lookup"><span data-stu-id="0205b-228">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="0205b-229">Некоторые примеры использования удаленных указанными типами нет представления не требуется.</span><span class="sxs-lookup"><span data-stu-id="0205b-229">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="0205b-230">Например удаленных в тип может содержать только статические свойства и члены и конструкторы не, и возвращает экземпляр типа отсутствуют методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="0205b-230">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="0205b-231">Если вы можете связаться удаленных экземпляров указан тип, необходимо учитывать следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="0205b-231">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="0205b-232">**Что такое стирания предоставленного типа?**</span><span class="sxs-lookup"><span data-stu-id="0205b-232">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="0205b-233">Стирание предоставленного типа — как тип отображается в скомпилированном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0205b-233">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="0205b-234">Стирания типа предоставленный класс удаленных всегда является первой не удалены базового типа в цепочке наследования типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-234">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="0205b-235">Всегда является стирания типа предоставленный интерфейс удаленных `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="0205b-235">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="0205b-236">**Что такое представления предоставленного типа**</span><span class="sxs-lookup"><span data-stu-id="0205b-236">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="0205b-237">Набор возможных объектов для удаленных указан тип, называются его представления.</span><span class="sxs-lookup"><span data-stu-id="0205b-237">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="0205b-238">В примере в этом документе, типы представлений всех удаленных предоставленный `Type1..Type100` всегда являются строковых объектов.</span><span class="sxs-lookup"><span data-stu-id="0205b-238">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="0205b-239">Все представления, предоставленного типа должен быть совместим с стирания предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-239">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="0205b-240">(В противном случае либо F# для использования поставщика типа, компилятор будет выдавать ошибку, или создается непроверяемый код .NET, который недопустим.</span><span class="sxs-lookup"><span data-stu-id="0205b-240">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="0205b-241">Поставщик типов не является допустимым, если он возвращает код, который предоставляет представление, которое является недопустимым.)</span><span class="sxs-lookup"><span data-stu-id="0205b-241">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="0205b-242">Это представление для предоставленных объектов можно выбрать с помощью любого из следующих методов, каждый из которых является очень распространенным:</span><span class="sxs-lookup"><span data-stu-id="0205b-242">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="0205b-243">Если просто строго типизированную оболочку подается на существующий тип .NET, часто имеет смысл для типа, чтобы стереть к этому типу, используйте экземпляры этого типа представления, или в виде.</span><span class="sxs-lookup"><span data-stu-id="0205b-243">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="0205b-244">Этот подход используется, когда большинство существующих методов этого типа по-прежнему имеет смысла при использовании строго типизированной версии.</span><span class="sxs-lookup"><span data-stu-id="0205b-244">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="0205b-245">Если вы хотите значительно создания API, который отличается от любого существующего API .NET, имеет смысл создать типы среды выполнения, которые будут стирания типа и представления для существующих.</span><span class="sxs-lookup"><span data-stu-id="0205b-245">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="0205b-246">В примере в этом документе используются строки для представления предоставленных объектов.</span><span class="sxs-lookup"><span data-stu-id="0205b-246">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="0205b-247">Часто возможно, можно использовать другие объекты, для представления.</span><span class="sxs-lookup"><span data-stu-id="0205b-247">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="0205b-248">Например словарь можно использовать как контейнер свойств:</span><span class="sxs-lookup"><span data-stu-id="0205b-248">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="0205b-249">Кроме того может определить тип в ваш поставщик типов, который будет использоваться во время выполнения для формирования представления, а также один или несколько операций среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="0205b-249">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="0205b-250">Если элементы затем можно создать экземпляры этого типа объектов:</span><span class="sxs-lookup"><span data-stu-id="0205b-250">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="0205b-251">В этом случае может (необязательно) служит этот тип стирания типа, указав этот тип как `baseType` при создании `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="0205b-251">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="0205b-252">Полученный опыт</span><span class="sxs-lookup"><span data-stu-id="0205b-252">Key Lessons</span></span>

<span data-ttu-id="0205b-253">Выше было рассмотрено, как создать простой поставщик стирания типа, который предоставляет широкий набор типов, свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="0205b-253">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="0205b-254">В этом разделе также объясняется понятие стирания типа, включая некоторые преимущества и недостатки предоставления удаленных типов от поставщика тип и обсуждается представления удаленных типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-254">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="0205b-255">Тип поставщика, использующего статические параметры</span><span class="sxs-lookup"><span data-stu-id="0205b-255">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="0205b-256">Возможность параметризовать поставщиков типов, статических данных делает возможными интересные ситуации, даже в случаях, когда поставщик не требуется доступ к любым локальным или удаленным данным.</span><span class="sxs-lookup"><span data-stu-id="0205b-256">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="0205b-257">В этом разделе вы узнаете некоторые основные методы объединения такой поставщик.</span><span class="sxs-lookup"><span data-stu-id="0205b-257">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="0205b-258">Тип проверки регулярного выражения поставщика</span><span class="sxs-lookup"><span data-stu-id="0205b-258">Type Checked Regex Provider</span></span>

<span data-ttu-id="0205b-259">Представьте, что вы хотите реализовать поставщик типов для регулярных выражений, который создает оболочку .NET <xref:System.Text.RegularExpressions.Regex> библиотеки в интерфейсе, который предоставляет следующие гарантии времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="0205b-259">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="0205b-260">Проверка того, является ли допустимым регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="0205b-260">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="0205b-261">Задание именованных свойств, основываясь на все имена групп в регулярном выражении.</span><span class="sxs-lookup"><span data-stu-id="0205b-261">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="0205b-262">В этом разделе показано, как создать с помощью поставщиков типов `RegexTyped` введите параметризует что шаблон регулярного выражения и обеспечивает следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="0205b-262">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="0205b-263">Компилятор сообщит об ошибке, если указанный шаблон не является допустимым, и поставщика типов можно извлечь группы из шаблона, таким образом, они будут доступны с помощью именованных свойств на совпадения.</span><span class="sxs-lookup"><span data-stu-id="0205b-263">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="0205b-264">При разработке поставщика типов, следует учитывать, как должен выглядеть его предоставленным API для конечных пользователей и как такая схема будет преобразовано в код .NET.</span><span class="sxs-lookup"><span data-stu-id="0205b-264">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="0205b-265">Приведенный ниже показано, как использовать такой API для получения компонентов области кода:</span><span class="sxs-lookup"><span data-stu-id="0205b-265">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="0205b-266">В следующем примере показано, как поставщик типов преобразует эти вызовы:</span><span class="sxs-lookup"><span data-stu-id="0205b-266">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="0205b-267">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="0205b-267">Note the following points:</span></span>

- <span data-ttu-id="0205b-268">Стандартный тип Regex представляет параметризованного `RegexTyped` типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-268">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="0205b-269">`RegexTyped` Конструктор приводит к вызову конструктора Regex, передавая статический тип аргумента для шаблона.</span><span class="sxs-lookup"><span data-stu-id="0205b-269">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="0205b-270">Результаты `Match` метод представлены стандартные <xref:System.Text.RegularExpressions.Match> типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-270">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="0205b-271">Каждой именованной группы приводит к указанного свойства, и обращение к свойству приводит к использованию индексатора при совпадении `Groups` коллекции.</span><span class="sxs-lookup"><span data-stu-id="0205b-271">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="0205b-272">Следующий код является основной логики для реализации такой поставщик, и в этом примере не включает добавление всех элементов в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="0205b-272">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="0205b-273">Сведения о каждой добавлен элемент см. соответствующий раздел далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0205b-273">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="0205b-274">Полный текст кода, загрузите образец с [ F# 3.0 образец пакета](https://archive.codeplex.com/?p=fsharp3sample) на веб-сайте CodePlex.</span><span class="sxs-lookup"><span data-stu-id="0205b-274">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

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

<span data-ttu-id="0205b-275">Обратите внимание на следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="0205b-275">Note the following points:</span></span>

- <span data-ttu-id="0205b-276">Поставщик типа принимает два параметра статического: `pattern`, который является обязательным и `options`, какие — дополнительными (так как значения по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0205b-276">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="0205b-277">Когда статические аргументы указаны, можно создать экземпляр регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="0205b-277">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="0205b-278">Этот экземпляр будет создания исключения, если регулярное выражение имеет неправильный формат, и эта ошибка будет выводиться пользователям.</span><span class="sxs-lookup"><span data-stu-id="0205b-278">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="0205b-279">В рамках `DefineStaticParameters` обратного вызова, определите тип, который будет возвращаться после аргументов.</span><span class="sxs-lookup"><span data-stu-id="0205b-279">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="0205b-280">Этот код задает `HideObjectMethods` значение true, чтобы возможности IntelliSense будет оставаться упрощенный.</span><span class="sxs-lookup"><span data-stu-id="0205b-280">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="0205b-281">Этот атрибут приводит к `Equals`, `GetHashCode`, `Finalize`, и `GetType` члены для подавления из списка IntelliSense для предоставленного объекта.</span><span class="sxs-lookup"><span data-stu-id="0205b-281">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="0205b-282">Использовании `obj` как базовый тип метода, но вы будете использовать `Regex` объект как представление времени выполнения этого типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0205b-282">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="0205b-283">Вызов `Regex` конструктор вызывает <xref:System.ArgumentException> при регулярное выражение является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="0205b-283">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="0205b-284">Компилятор перехватывает это исключение и сообщает пользователю сообщение об ошибке, во время компиляции, а также в редакторе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0205b-284">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="0205b-285">Это исключение позволяет регулярные выражения для проверки без запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="0205b-285">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="0205b-286">Так как она не содержит все значимые методы и свойства типа, определенного выше еще не полезно.</span><span class="sxs-lookup"><span data-stu-id="0205b-286">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="0205b-287">Сначала добавьте статический `IsMatch` метод:</span><span class="sxs-lookup"><span data-stu-id="0205b-287">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="0205b-288">Предыдущий код определяет метод `IsMatch`, который принимает в качестве входных данных строку и возвращает `bool`.</span><span class="sxs-lookup"><span data-stu-id="0205b-288">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="0205b-289">Единственной сложностью является использование `args` аргумент `InvokeCode` определения.</span><span class="sxs-lookup"><span data-stu-id="0205b-289">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="0205b-290">В этом примере `args` является список предложений, который представляет аргументы для этого метода.</span><span class="sxs-lookup"><span data-stu-id="0205b-290">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="0205b-291">Если метод является методом экземпляра, первый аргумент представляет `this` аргумент.</span><span class="sxs-lookup"><span data-stu-id="0205b-291">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="0205b-292">Тем не менее для статического метода, перечислены все, что явные аргументы метода.</span><span class="sxs-lookup"><span data-stu-id="0205b-292">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="0205b-293">Обратите внимание, что тип значения, заключенные в кавычки должен совпадать с заданным типом возвращаемого значения (в этом случае `bool`).</span><span class="sxs-lookup"><span data-stu-id="0205b-293">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="0205b-294">Также Обратите внимание, что этот код использует `AddXmlDoc` метод, чтобы убедиться в том, что указанный метод также имеет полезные документации, можно указать через IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0205b-294">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="0205b-295">Добавьте экземпляр метода Match.</span><span class="sxs-lookup"><span data-stu-id="0205b-295">Next, add an instance Match method.</span></span> <span data-ttu-id="0205b-296">Тем не менее, этот метод должен возвращать значение заданного `Match` так, чтобы группы может осуществляться в сильно типизированной форме.</span><span class="sxs-lookup"><span data-stu-id="0205b-296">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="0205b-297">Таким образом, сперва надо объявить `Match` типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-297">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="0205b-298">Так как этот тип зависит от шаблона, переданному как статический аргумент, этот тип должен быть вложен в определении параметризованного типа:</span><span class="sxs-lookup"><span data-stu-id="0205b-298">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="0205b-299">Затем добавьте одно свойство в тип соответствия для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="0205b-299">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="0205b-300">Во время выполнения, соответствие представляется в виде <xref:System.Text.RegularExpressions.Match> значение, поэтому необходимо использовать предложение, которое определяет свойство <xref:System.Text.RegularExpressions.Match.Groups> индексированное свойство, чтобы получить соответствующую группу.</span><span class="sxs-lookup"><span data-stu-id="0205b-300">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="0205b-301">Опять же Обратите внимание на то, что вы добавляете XML-документации для указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="0205b-301">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="0205b-302">Также Обратите внимание, что можно прочитать свойство, если `GetterCode` предоставляются функции и свойства могут записываться таким образом, если `SetterCode` функция предоставляется, поэтому результирующее свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0205b-302">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="0205b-303">Теперь вы можете создать метод экземпляра, который возвращает значение данного `Match` типа:</span><span class="sxs-lookup"><span data-stu-id="0205b-303">Now you can create an instance method that returns a value of this `Match` type:</span></span>

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

<span data-ttu-id="0205b-304">Так как вы создаете методом экземпляра `args.[0]` представляет `RegexTyped` экземпляр, на котором вызывается метод, и `args.[1]` является входного аргумента.</span><span class="sxs-lookup"><span data-stu-id="0205b-304">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="0205b-305">Наконец Предоставьте конструктор для создания экземпляров предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-305">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="0205b-306">Конструктор просто стирает для создания стандартного экземпляра регулярных выражений .NET, который упаковывается в объект еще раз, так как `obj` является стирания предоставленного типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-306">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="0205b-307">После этого изменения пример использования API, который указан выше работает ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="0205b-307">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="0205b-308">Ниже приведен полный и последнее:</span><span class="sxs-lookup"><span data-stu-id="0205b-308">The following code is complete and final:</span></span>

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

### <a name="key-lessons"></a><span data-ttu-id="0205b-309">Полученный опыт</span><span class="sxs-lookup"><span data-stu-id="0205b-309">Key Lessons</span></span>

<span data-ttu-id="0205b-310">В этом разделе описано создание поставщика типов, которая работает на его статические параметры.</span><span class="sxs-lookup"><span data-stu-id="0205b-310">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="0205b-311">Поставщик проверяет параметр static и предоставляет операции, основанные на его значение.</span><span class="sxs-lookup"><span data-stu-id="0205b-311">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="0205b-312">Поставщик типа, который поддерживается службой локальных данных</span><span class="sxs-lookup"><span data-stu-id="0205b-312">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="0205b-313">Часто можно поставщиков типов для представления API, основываясь на не только статические параметры, но данные из локальных или удаленных систем.</span><span class="sxs-lookup"><span data-stu-id="0205b-313">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="0205b-314">В этом разделе рассматриваются поставщиков типов, основанных на локальные данные, такие как локальные файлы данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-314">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="0205b-315">Поставщик простой CSV-файлов</span><span class="sxs-lookup"><span data-stu-id="0205b-315">Simple CSV File Provider</span></span>

<span data-ttu-id="0205b-316">В качестве простого примера рассмотрим поставщик типов для доступа к научных данных в формате с разделителями разделенных запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="0205b-316">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="0205b-317">В этом разделе предполагается, что CSV-файлы содержат строку заголовка, следуют данных с плавающей запятой, как показано в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="0205b-317">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="0205b-318">Расстояние (счетчик)</span><span class="sxs-lookup"><span data-stu-id="0205b-318">Distance (meter)</span></span>|<span data-ttu-id="0205b-319">Время (секунды)</span><span class="sxs-lookup"><span data-stu-id="0205b-319">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="0205b-320">50.0</span><span class="sxs-lookup"><span data-stu-id="0205b-320">50.0</span></span>|<span data-ttu-id="0205b-321">3.7</span><span class="sxs-lookup"><span data-stu-id="0205b-321">3.7</span></span>|
|<span data-ttu-id="0205b-322">100.0</span><span class="sxs-lookup"><span data-stu-id="0205b-322">100.0</span></span>|<span data-ttu-id="0205b-323">5.2</span><span class="sxs-lookup"><span data-stu-id="0205b-323">5.2</span></span>|
|<span data-ttu-id="0205b-324">150.0</span><span class="sxs-lookup"><span data-stu-id="0205b-324">150.0</span></span>|<span data-ttu-id="0205b-325">6.4</span><span class="sxs-lookup"><span data-stu-id="0205b-325">6.4</span></span>|

<span data-ttu-id="0205b-326">В этом разделе показано, как указать тип, который можно использовать для получения строк с `Distance` свойство типа `float<meter>` и `Time` свойство типа `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="0205b-326">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="0205b-327">Для простоты предполагается следующее:</span><span class="sxs-lookup"><span data-stu-id="0205b-327">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="0205b-328">Имена заголовков делятся без единицы измерения или в формате «Имя (единицы)» и не содержать запятые.</span><span class="sxs-lookup"><span data-stu-id="0205b-328">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="0205b-329">Единицы — все единицы международной системы (SI) в качестве [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames модуля (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) модуль определяет.</span><span class="sxs-lookup"><span data-stu-id="0205b-329">Units are all System International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="0205b-330">Единицы просты (например, вести учет), а не составные (например, счетчик в секунду).</span><span class="sxs-lookup"><span data-stu-id="0205b-330">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="0205b-331">Все столбцы содержат данных с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="0205b-331">All columns contain floating point data.</span></span>

<span data-ttu-id="0205b-332">Более полный поставщик может ослабить эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="0205b-332">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="0205b-333">Еще раз первым делом необходимо учитывать, как должен выглядеть интерфейс API.</span><span class="sxs-lookup"><span data-stu-id="0205b-333">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="0205b-334">Учитывая `info.csv` файл с содержимым из предыдущей таблицы (в формате с разделителями запятыми), пользователи поставщика, должны иметь возможность писать код, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="0205b-334">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="0205b-335">В этом случае компилятор должен преобразовать эти вызовы во что-то, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0205b-335">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="0205b-336">Оптимальной перевод потребуется поставщик типов для определения настоящие `CsvFile` типа в сборке поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-336">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="0205b-337">Поставщики типов часто используют несколько вспомогательные типы и методы для создания оболочки важных логических.</span><span class="sxs-lookup"><span data-stu-id="0205b-337">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="0205b-338">Поскольку меры будут удалены во время выполнения, можно использовать `float[]` как удаленный тип, для строки.</span><span class="sxs-lookup"><span data-stu-id="0205b-338">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="0205b-339">Компилятор будет рассматривать разные столбцы как разные меры типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-339">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="0205b-340">Например, первый столбец в нашем примере имеет тип `float<meter>`, а второй — `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="0205b-340">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="0205b-341">Тем не менее вместо удаленных представление может оставаться довольно просто.</span><span class="sxs-lookup"><span data-stu-id="0205b-341">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="0205b-342">В следующем коде показано ядро реализации.</span><span class="sxs-lookup"><span data-stu-id="0205b-342">The following code shows the core of the implementation.</span></span>

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

<span data-ttu-id="0205b-343">Обратите внимание на следующие аспекты реализации:</span><span class="sxs-lookup"><span data-stu-id="0205b-343">Note the following points about the implementation:</span></span>

- <span data-ttu-id="0205b-344">Перегруженные конструкторы позволяют исходный файл или ту, которая имеет идентичные схемы для чтения.</span><span class="sxs-lookup"><span data-stu-id="0205b-344">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="0205b-345">Этот шаблон является наиболее распространенным, при написании поставщика типа для источников данных локальным или удаленным, и этот шаблон позволяет локального файла для использования в качестве шаблона для удаленных данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-345">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="0205b-346">Можно использовать [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) значение, которое передается в конструктор поставщика типа для разрешения относительных имен файла.</span><span class="sxs-lookup"><span data-stu-id="0205b-346">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="0205b-347">Можно использовать `AddDefinitionLocation` метод для определения местоположения указанные свойства.</span><span class="sxs-lookup"><span data-stu-id="0205b-347">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="0205b-348">Таким образом Если вы используете `Go To Definition` указанное свойство CSV-файл откроется в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0205b-348">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="0205b-349">Можно использовать `ProvidedMeasureBuilder` типов для поиска SI единицы измерения и создания соответствующего `float<_>` типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-349">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="0205b-350">Полученный опыт</span><span class="sxs-lookup"><span data-stu-id="0205b-350">Key Lessons</span></span>

<span data-ttu-id="0205b-351">В этом разделе описано создание поставщика типов для локальный источник данных с простой схемой, содержащийся в самого источника данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-351">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="0205b-352">Продвигаясь дальше</span><span class="sxs-lookup"><span data-stu-id="0205b-352">Going Further</span></span>

<span data-ttu-id="0205b-353">В следующих разделах приведены рекомендации для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="0205b-353">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="0205b-354">Рассмотрим скомпилированный код для удаленных типов</span><span class="sxs-lookup"><span data-stu-id="0205b-354">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="0205b-355">Чтобы получить некоторое представление о том, как использование поставщика типов соответствует код, который создается, рассмотрим следующую функцию с помощью `HelloWorldTypeProvider` , используемый этой статьи.</span><span class="sxs-lookup"><span data-stu-id="0205b-355">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="0205b-356">Вот изображение декомпилированным с помощью ildasm.exe результирующий код:</span><span class="sxs-lookup"><span data-stu-id="0205b-356">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

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

<span data-ttu-id="0205b-357">Как показано в примере, все упоминания типа `Type1` и `InstanceProperty` свойства были удалены, оставляя участвующие только операции с типами среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0205b-357">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="0205b-358">Проектирование и соглашения об именовании для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="0205b-358">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="0205b-359">Следует соблюдайте следующие соглашения, при разработке поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-359">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="0205b-360">**Поставщики для подключения к протоколов** в общем случае имена большинство библиотек DLL поставщика для данных и служб подключения протоколов, таких как OData или SQL-подключений, должны заканчиваться `TypeProvider` или `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="0205b-360">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="0205b-361">Например используйте имя библиотеки DLL, которое примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="0205b-361">For example, use a DLL name that resembles the following string:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.dll
```

<span data-ttu-id="0205b-362">Убедитесь, что предоставленный типы являются членами соответствующего пространства имен и указывает реализуемый протокол подключения:</span><span class="sxs-lookup"><span data-stu-id="0205b-362">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="0205b-363">**Программа поставщиков для общего кода**.</span><span class="sxs-lookup"><span data-stu-id="0205b-363">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="0205b-364">Для программы поставщика типов, например для регулярных выражений поставщик типов может быть частью базовой библиотеки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0205b-364">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="0205b-365">В этом случае предоставленный тип будет выглядеть в соответствующий момент в соответствии с соглашениями разработки обычных .NET:</span><span class="sxs-lookup"><span data-stu-id="0205b-365">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="0205b-366">**Источники данных одноэлементный**.</span><span class="sxs-lookup"><span data-stu-id="0205b-366">**Singleton Data Sources**.</span></span> <span data-ttu-id="0205b-367">Некоторые поставщики типов и предоставлять только данные, так как к одного выделенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="0205b-367">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="0205b-368">В этом случае следует удалить `TypeProvider` суффикс и используйте соглашения об обычном для .NET:</span><span class="sxs-lookup"><span data-stu-id="0205b-368">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="0205b-369">Дополнительные сведения см. в разделе `GetConnection` разработать соглашение, которое описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0205b-369">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="0205b-370">Конструктивные шаблоны для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="0205b-370">Design Patterns for Type Providers</span></span>

<span data-ttu-id="0205b-371">В следующих разделах шаблоны проектирования, которые можно использовать при разработке поставщиков типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-371">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="0205b-372">Шаблон разработки GetConnection</span><span class="sxs-lookup"><span data-stu-id="0205b-372">The GetConnection Design Pattern</span></span>

<span data-ttu-id="0205b-373">Большинство поставщиков типов должен быть записан использовать `GetConnection` шаблон, который используется поставщиками типов в FSharp.Data.TypeProviders.dll, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0205b-373">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="0205b-374">Поставщики типов с удаленным данным и службам</span><span class="sxs-lookup"><span data-stu-id="0205b-374">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="0205b-375">Перед созданием поставщик типа, который поддерживается службой удаленным данным и службам, необходимо учитывать ряд проблем, свойственных подключенных программирования.</span><span class="sxs-lookup"><span data-stu-id="0205b-375">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="0205b-376">Эти проблемы включают следующее:</span><span class="sxs-lookup"><span data-stu-id="0205b-376">These issues include the following considerations:</span></span>

- <span data-ttu-id="0205b-377">Сопоставление схем</span><span class="sxs-lookup"><span data-stu-id="0205b-377">schema mapping</span></span>

- <span data-ttu-id="0205b-378">жизнеспособность и недействительности при наличии изменений схемы</span><span class="sxs-lookup"><span data-stu-id="0205b-378">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="0205b-379">Кэширование схем</span><span class="sxs-lookup"><span data-stu-id="0205b-379">schema caching</span></span>

- <span data-ttu-id="0205b-380">асинхронные реализации операций доступа к данным</span><span class="sxs-lookup"><span data-stu-id="0205b-380">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="0205b-381">Поддержка запросов, включая запросы LINQ</span><span class="sxs-lookup"><span data-stu-id="0205b-381">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="0205b-382">учетные данные и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="0205b-382">credentials and authentication</span></span>

<span data-ttu-id="0205b-383">В этом разделе не рассматриваются эти дополнительные проблемы.</span><span class="sxs-lookup"><span data-stu-id="0205b-383">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="0205b-384">Дополнительные методы разработки</span><span class="sxs-lookup"><span data-stu-id="0205b-384">Additional Authoring Techniques</span></span>

<span data-ttu-id="0205b-385">При написании собственных поставщиков типов, можно использовать из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="0205b-385">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="0205b-386">Создание типов и членов по запросу</span><span class="sxs-lookup"><span data-stu-id="0205b-386">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="0205b-387">ProvidedType API откладывала версиях AddMember.</span><span class="sxs-lookup"><span data-stu-id="0205b-387">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="0205b-388">Эти версии используются для создания пространств по запросу типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-388">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="0205b-389">Типы массивов и экземпляров универсального типа</span><span class="sxs-lookup"><span data-stu-id="0205b-389">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="0205b-390">Предоставленные члены, (, подписи включают типы массивов, типы byref и упрощено создание экземпляров универсальных типов), внесенные с помощью обычного `MakeArrayType`, `MakePointerType`, и `MakeGenericType` на любом экземпляре <xref:System.Type>, в том числе `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="0205b-390">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="0205b-391">В некоторых случаях может потребоваться использовать вспомогательный модуль `ProvidedTypeBuilder.MakeGenericType`.</span><span class="sxs-lookup"><span data-stu-id="0205b-391">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="0205b-392">См. в разделе [документации по пакету SDK поставщика типа](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="0205b-392">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="0205b-393">Предоставляя единицы измерения заметок</span><span class="sxs-lookup"><span data-stu-id="0205b-393">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="0205b-394">ProvidedTypes API предоставляет вспомогательные методы для предоставления мер заметок.</span><span class="sxs-lookup"><span data-stu-id="0205b-394">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="0205b-395">Например, чтобы указать тип `float<kg>`, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0205b-395">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="0205b-396">Для обеспечения типа `Nullable<decimal<kg/m^2>>`, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0205b-396">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="0205b-397">Доступ к ресурсам локальной скрипт или локальной для проекта</span><span class="sxs-lookup"><span data-stu-id="0205b-397">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="0205b-398">Каждый экземпляр поставщика типа может быть задан `TypeProviderConfig` значение во время построения.</span><span class="sxs-lookup"><span data-stu-id="0205b-398">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="0205b-399">Это значение содержит «разрешение папку» для поставщика (то есть папка проекта для компиляции или каталог, содержащий сценарий), список сборок, на которые имеются ссылки и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="0205b-399">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="0205b-400">Недействительность</span><span class="sxs-lookup"><span data-stu-id="0205b-400">Invalidation</span></span>

<span data-ttu-id="0205b-401">Поставщики могут вызывать сигналы о недействительности для уведомления F# языковой службы, которая предположения схемы может измениться.</span><span class="sxs-lookup"><span data-stu-id="0205b-401">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="0205b-402">В случае аннулирования typecheck Повторено, если поставщик находится в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0205b-402">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="0205b-403">Этот сигнал будет игнорироваться, если поставщик размещается в F# интерактивные или F# компилятор (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="0205b-403">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="0205b-404">Кэширование сведений о схеме</span><span class="sxs-lookup"><span data-stu-id="0205b-404">Caching Schema Information</span></span>

<span data-ttu-id="0205b-405">Поставщики часто необходимо кэшировать доступ к информации схемы.</span><span class="sxs-lookup"><span data-stu-id="0205b-405">Providers must often cache access to schema information.</span></span> <span data-ttu-id="0205b-406">Кэшированные данные должны храниться с помощью имени файла, которое задано как параметр статического или сведений о пользователях.</span><span class="sxs-lookup"><span data-stu-id="0205b-406">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="0205b-407">Пример кэширования схемы — `LocalSchemaFile` параметра в тип поставщиков в `FSharp.Data.TypeProviders` сборки.</span><span class="sxs-lookup"><span data-stu-id="0205b-407">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="0205b-408">В реализации этих поставщиков этот статический параметр указывает поставщика типов для использования данных схемы в указанный локальный файл вместо обращения к источнику данных по сети.</span><span class="sxs-lookup"><span data-stu-id="0205b-408">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="0205b-409">Для использования кэшированных данных схемы, необходимо также задать параметр static `ForceUpdate` для `false`.</span><span class="sxs-lookup"><span data-stu-id="0205b-409">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="0205b-410">Похожий прием можно использовать для доступа к данным сетевой и автономный режим.</span><span class="sxs-lookup"><span data-stu-id="0205b-410">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="0205b-411">Резервная сборка</span><span class="sxs-lookup"><span data-stu-id="0205b-411">Backing Assembly</span></span>

<span data-ttu-id="0205b-412">При компиляции `.dll` или `.exe` файл, DLL-файл резервного для создаваемых типов статически связываются с итоговой сборки.</span><span class="sxs-lookup"><span data-stu-id="0205b-412">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="0205b-413">Эта ссылка создается путем копирования определения типов промежуточного языка (IL) и все управляемые ресурсы из находится резервная сборка, в окончательную сборку.</span><span class="sxs-lookup"><span data-stu-id="0205b-413">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="0205b-414">При использовании F# Interactive, DLL-файла, резервное, не будут копироваться и вместо этого загружаются непосредственно в F# интерактивного процесса.</span><span class="sxs-lookup"><span data-stu-id="0205b-414">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="0205b-415">Исключения и диагностики из поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="0205b-415">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="0205b-416">Все случаи использования все элементы из существующих может вызывать исключения.</span><span class="sxs-lookup"><span data-stu-id="0205b-416">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="0205b-417">Во всех случаях если поставщик типа создает исключение, компилятор узла атрибуты ошибку поставщику определенного типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-417">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="0205b-418">Тип поставщика исключения никогда не должно приводить внутренних ошибках компилятора.</span><span class="sxs-lookup"><span data-stu-id="0205b-418">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="0205b-419">Поставщики типов не может сообщать об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0205b-419">Type providers can't report warnings.</span></span>

- <span data-ttu-id="0205b-420">Когда поставщик типа размещается в F# компилятора, F# среды разработки или F# Interactive, перехватываются все исключения из этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0205b-420">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="0205b-421">Свойство сообщения всегда текст ошибки, и появляется не выполняется трассировка стека.</span><span class="sxs-lookup"><span data-stu-id="0205b-421">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="0205b-422">Если вы собираетесь исключение, можно создавать следующие примеры: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="0205b-422">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="0205b-423">Предоставляя созданных типов</span><span class="sxs-lookup"><span data-stu-id="0205b-423">Providing Generated Types</span></span>

<span data-ttu-id="0205b-424">На данный момент в этом документе показано, как обеспечить удаленных типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-424">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="0205b-425">Можно также использовать механизм поставщика типа в F# для предоставления созданных типов, который добавляются как реальные определениях типов .NET в программу пользователей.</span><span class="sxs-lookup"><span data-stu-id="0205b-425">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="0205b-426">Вы должны ссылаться на созданный предоставляемые типы с помощью определения типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-426">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="0205b-427">0,2 ProvidedTypes вспомогательный код, который является частью F# версии 3.0 имеет только ограниченную поддержку для предоставления созданных типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-427">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="0205b-428">Следующие инструкции должны выполняться условия для определения создаваемого типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-428">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="0205b-429">`isErased` должно быть присвоено `false`.</span><span class="sxs-lookup"><span data-stu-id="0205b-429">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="0205b-430">Необходимо добавить созданный тип для заново созданного `ProvidedAssembly()`, который представляет контейнер для созданного кода фрагментов.</span><span class="sxs-lookup"><span data-stu-id="0205b-430">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="0205b-431">Поставщик должен иметь сборку, которая содержит фактический резервного .NET DLL-файл, соответствующий файл DLL-файл на диске.</span><span class="sxs-lookup"><span data-stu-id="0205b-431">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="0205b-432">Правила и ограничения</span><span class="sxs-lookup"><span data-stu-id="0205b-432">Rules and Limitations</span></span>

<span data-ttu-id="0205b-433">При написании поставщиков типов, примите во внимание следующие правила и ограничения.</span><span class="sxs-lookup"><span data-stu-id="0205b-433">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="0205b-434">Указанные типы должен быть доступен</span><span class="sxs-lookup"><span data-stu-id="0205b-434">Provided types must be reachable</span></span>

<span data-ttu-id="0205b-435">Все входящие типы должны быть доступны с невложенными типы.</span><span class="sxs-lookup"><span data-stu-id="0205b-435">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="0205b-436">Типы невложенными предоставляется в вызове `TypeProviderForNamespaces` конструктор или вызов `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="0205b-436">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="0205b-437">Например, если поставщик предоставляет тип `StaticClass.P : T`, необходимо убедиться, что T является типом невложенными или вложенными в один.</span><span class="sxs-lookup"><span data-stu-id="0205b-437">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="0205b-438">Например, некоторые поставщики имеют статический класс, такие как `DataTypes` , содержащие такие `T1, T2, T3, ...` типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-438">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="0205b-439">В противном случае ошибка сообщает, что была обнаружена ссылка на тип "T" в сборке A, но не удалось найти тип в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="0205b-439">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="0205b-440">При появлении этой ошибки убедитесь, что все подтипы можно получить доступ из поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-440">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="0205b-441">Примечание. Эти `T1, T2, T3...` типы называются *на лету* типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-441">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="0205b-442">Не забудьте поместить их в пространство имен доступны или родительского типа.</span><span class="sxs-lookup"><span data-stu-id="0205b-442">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="0205b-443">Ограничения механизма тип поставщика</span><span class="sxs-lookup"><span data-stu-id="0205b-443">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="0205b-444">Механизм поставщика типа в F# имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="0205b-444">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="0205b-445">Базовая инфраструктура для поставщиков типов в F# не поддерживает универсальные типы или предоставленный универсальных методов.</span><span class="sxs-lookup"><span data-stu-id="0205b-445">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="0205b-446">Механизм не поддерживает вложенные типы с статические параметры.</span><span class="sxs-lookup"><span data-stu-id="0205b-446">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="0205b-447">Советы по разработке</span><span class="sxs-lookup"><span data-stu-id="0205b-447">Development Tips</span></span>

<span data-ttu-id="0205b-448">Следующие советы могут оказаться полезными во время разработки:</span><span class="sxs-lookup"><span data-stu-id="0205b-448">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="0205b-449">Запустите два экземпляра Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0205b-449">Run two instances of Visual Studio</span></span>

<span data-ttu-id="0205b-450">Можно разрабатывать в один экземпляр поставщика типов и проверьте его поставщик в другой, так как тест интегрированная среда разработки будет установить блокировку на DLL-файл, который предотвращает перестраивается поставщика типов.</span><span class="sxs-lookup"><span data-stu-id="0205b-450">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="0205b-451">Таким образом при создании поставщика в первом экземпляре, а затем необходимо повторно открыть второй экземпляр после построения поставщика необходимо закрыть второй экземпляр Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0205b-451">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="0205b-452">Отладка с помощью вызовов fsc.exe поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="0205b-452">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="0205b-453">Поставщики типов можно вызвать с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="0205b-453">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="0205b-454">fsc.exe ( F# компилятора командной строки)</span><span class="sxs-lookup"><span data-stu-id="0205b-454">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="0205b-455">fsi.exe ( F# интерактивный компилятор)</span><span class="sxs-lookup"><span data-stu-id="0205b-455">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="0205b-456">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0205b-456">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="0205b-457">Поставщики типов часто можно отлаживать проще всего с помощью fsc.exe в файл тестового скрипта (например, файл script.fsx).</span><span class="sxs-lookup"><span data-stu-id="0205b-457">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="0205b-458">Можно запустить отладчик из командной строки.</span><span class="sxs-lookup"><span data-stu-id="0205b-458">You can launch a debugger from a command prompt.</span></span>

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="0205b-459">Можно использовать ведение журнала печать в stdout.</span><span class="sxs-lookup"><span data-stu-id="0205b-459">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="0205b-460">См. также</span><span class="sxs-lookup"><span data-stu-id="0205b-460">See also</span></span>

- [<span data-ttu-id="0205b-461">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="0205b-461">Type Providers</span></span>](index.md)
- [<span data-ttu-id="0205b-462">Тип поставщика SDK</span><span class="sxs-lookup"><span data-stu-id="0205b-462">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
