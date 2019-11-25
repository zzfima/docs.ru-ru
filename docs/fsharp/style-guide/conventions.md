---
title: Соглашения о написании кода на F#
description: Ознакомьтесь с общими правилами и идиомами при F# написании кода.
ms.date: 11/04/2019
ms.openlocfilehash: 60eff6392d71caa54eeb438f2f6ba9db910f1bc1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978230"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="329ff-103">Соглашения о написании кода на F#</span><span class="sxs-lookup"><span data-stu-id="329ff-103">F# coding conventions</span></span>

<span data-ttu-id="329ff-104">Следующие соглашения формируются из опыта работы с большими F# кодовыми средами.</span><span class="sxs-lookup"><span data-stu-id="329ff-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="329ff-105">[Пять принципов работы с хорошим F# кодом](index.md#five-principles-of-good-f-code) являются основой каждой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="329ff-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="329ff-106">Они связаны с [ F# рекомендациями по проектированию компонентов](component-design-guidelines.md), но применимы для F# любого кода, а не только для таких компонентов, как библиотеки.</span><span class="sxs-lookup"><span data-stu-id="329ff-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="329ff-107">Организация кода</span><span class="sxs-lookup"><span data-stu-id="329ff-107">Organizing code</span></span>

<span data-ttu-id="329ff-108">F#два основных способа организации кода: модули и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="329ff-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="329ff-109">Они похожи, но имеют следующие отличия.</span><span class="sxs-lookup"><span data-stu-id="329ff-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="329ff-110">Пространства имен компилируются как пространства имен .NET.</span><span class="sxs-lookup"><span data-stu-id="329ff-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="329ff-111">Модули компилируются как статические классы.</span><span class="sxs-lookup"><span data-stu-id="329ff-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="329ff-112">Пространства имен всегда имеют верхний уровень.</span><span class="sxs-lookup"><span data-stu-id="329ff-112">Namespaces are always top level.</span></span> <span data-ttu-id="329ff-113">Модули могут быть верхнего уровня и вложены в другие модули.</span><span class="sxs-lookup"><span data-stu-id="329ff-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="329ff-114">Пространства имен могут охватывать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="329ff-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="329ff-115">Модули не могут.</span><span class="sxs-lookup"><span data-stu-id="329ff-115">Modules cannot.</span></span>
* <span data-ttu-id="329ff-116">Модули можно снабдить `[<RequireQualifiedAccess>]` и `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="329ff-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="329ff-117">Следующие рекомендации помогут вам использовать их для организации кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="329ff-118">Предпочитать пространства имен на верхнем уровне</span><span class="sxs-lookup"><span data-stu-id="329ff-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="329ff-119">Для любого общедоступного кода пространства имен являются предпочтительными для модулей на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="329ff-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="329ff-120">Поскольку они компилируются как пространства имен .NET, они могут быть потреблены от C# без каких-либо проблем.</span><span class="sxs-lookup"><span data-stu-id="329ff-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="329ff-121">Использование модуля верхнего уровня может не отличаться при вызове только из F#, но для C# потребителей вызывающие объекты могут быть удивлены тем, что необходимо уточнить`MyClass`с помощью модуля`MyCode`.</span><span class="sxs-lookup"><span data-stu-id="329ff-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="329ff-122">Тщательное применение `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="329ff-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="329ff-123">Конструкция `[<AutoOpen>]` может засоряла область действия, которая доступна для вызывающих объектов, и ответ на то, что поступает от "волшебного".</span><span class="sxs-lookup"><span data-stu-id="329ff-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="329ff-124">Как правило, это не хорошая вещь.</span><span class="sxs-lookup"><span data-stu-id="329ff-124">This is generally not a good thing.</span></span> <span data-ttu-id="329ff-125">Исключением из F# этого правила является сама основная библиотека (хотя этот факт также является битом спорной).</span><span class="sxs-lookup"><span data-stu-id="329ff-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="329ff-126">Однако это удобство, если у вас есть вспомогательная функциональность для общедоступного API, который вы хотите упорядочить отдельно от этого общедоступного API.</span><span class="sxs-lookup"><span data-stu-id="329ff-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="329ff-127">Это позволяет четко отделить сведения о реализации от открытого API функции, не требуя полного определения вспомогательного метода при каждом его вызове.</span><span class="sxs-lookup"><span data-stu-id="329ff-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="329ff-128">Кроме того, предоставление методов расширения и построителей выражений на уровне пространства имен можно аккуратно выразить с помощью `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="329ff-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="329ff-129">Используйте `[<RequireQualifiedAccess>]` всякий раз, когда имена могут конфликтовать, или вы считаете, что они помогают удобочитаемости</span><span class="sxs-lookup"><span data-stu-id="329ff-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="329ff-130">Добавление атрибута `[<RequireQualifiedAccess>]` к модулю означает, что модуль не может быть открыт и что ссылки на элементы модуля должны явно иметь полный доступ.</span><span class="sxs-lookup"><span data-stu-id="329ff-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="329ff-131">Например, модуль `Microsoft.FSharp.Collections.List` имеет этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="329ff-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="329ff-132">Это полезно, когда функции и значения в модуле имеют имена, которые, скорее всего, конфликтуют с именами в других модулях.</span><span class="sxs-lookup"><span data-stu-id="329ff-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="329ff-133">Обязательное получение полного доступа может значительно увеличить долгосрочное обслуживание и развитию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="329ff-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="329ff-134">Инструкции сортировки `open` топологически</span><span class="sxs-lookup"><span data-stu-id="329ff-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="329ff-135">В F#порядок объявлений имеет значение, включая инструкции `open`.</span><span class="sxs-lookup"><span data-stu-id="329ff-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="329ff-136">Это не похоже C#на то, где воздействие`using`и`using static`не зависит от порядка этих инструкций в файле.</span><span class="sxs-lookup"><span data-stu-id="329ff-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="329ff-137">В F#элементы, открытые в области, могут уже быть скрыты другими.</span><span class="sxs-lookup"><span data-stu-id="329ff-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="329ff-138">Это означает, что Переупорядочение инструкций `open` может изменить значение кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="329ff-139">В результате некоторая Любая произвольная сортировка всех инструкций `open` (например, буквенно-цифровых) обычно не рекомендуется, допустим вы создаете другое поведение, которое вы можете ожидать.</span><span class="sxs-lookup"><span data-stu-id="329ff-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="329ff-140">Вместо этого рекомендуется отсортировать их [топологически](https://en.wikipedia.org/wiki/Topological_sorting); то есть закажите операторы `open` в том порядке, в котором определены _уровни_ системы.</span><span class="sxs-lookup"><span data-stu-id="329ff-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="329ff-141">Также можно учитывать алфавитно-цифровые сортировки в разных слоях топологическом.</span><span class="sxs-lookup"><span data-stu-id="329ff-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="329ff-142">Ниже приведен пример сортировки топологическом для файла общедоступного API F# -интерфейса службы компилятора:</span><span class="sxs-lookup"><span data-stu-id="329ff-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="329ff-143">Обратите внимание, что разрыв строки разделяет слои топологическом, при этом каждый слой сортируется в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="329ff-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="329ff-144">Это четко организует код без случайного затенения значений.</span><span class="sxs-lookup"><span data-stu-id="329ff-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="329ff-145">Использование классов для хранения значений, имеющих побочные эффекты</span><span class="sxs-lookup"><span data-stu-id="329ff-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="329ff-146">Существует много случаев, когда инициализация значения может иметь побочные эффекты, такие как создание экземпляра контекста для базы данных или другого удаленного ресурса.</span><span class="sxs-lookup"><span data-stu-id="329ff-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="329ff-147">Он позволяет инициализировать такие вещи в модуле и использовать его в последующих функциях:</span><span class="sxs-lookup"><span data-stu-id="329ff-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="329ff-148">Это неплохое идея по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="329ff-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="329ff-149">Во-первых, Конфигурация приложения помещается в базу кода с помощью `dep1` и `dep2`.</span><span class="sxs-lookup"><span data-stu-id="329ff-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="329ff-150">Это сложно поддерживать в больших базах кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="329ff-151">Во вторых, статически инициализированные данные не должны содержать значения, которые не являются потокобезопасными, если компонент будет использовать несколько потоков.</span><span class="sxs-lookup"><span data-stu-id="329ff-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="329ff-152">Это явно нарушается `dep3`.</span><span class="sxs-lookup"><span data-stu-id="329ff-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="329ff-153">Наконец, инициализация модуля компилируется в статический конструктор для всей единицы компиляции.</span><span class="sxs-lookup"><span data-stu-id="329ff-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="329ff-154">Если какая-либо ошибка возникает при инициализации значения с привязкой let в этом модуле, она переносится в качестве `TypeInitializationException`, которая кэшируется в течение всего времени существования приложения.</span><span class="sxs-lookup"><span data-stu-id="329ff-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="329ff-155">Это может быть трудно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="329ff-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="329ff-156">Обычно существует внутреннее исключение, которое можно попытаться определить, но в противном случае нет сведений о причине возникновения основной причины.</span><span class="sxs-lookup"><span data-stu-id="329ff-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="329ff-157">Вместо этого просто используйте простой класс для хранения зависимостей:</span><span class="sxs-lookup"><span data-stu-id="329ff-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="329ff-158">Это позволяет выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="329ff-158">This enables the following:</span></span>

1. <span data-ttu-id="329ff-159">Отправка любого зависимого состояния вне самого API.</span><span class="sxs-lookup"><span data-stu-id="329ff-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="329ff-160">Теперь конфигурацию можно выполнять за пределами API.</span><span class="sxs-lookup"><span data-stu-id="329ff-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="329ff-161">Ошибки инициализации зависимых значений, скорее всего, не будут пере`TypeInitializationException`ся в манифест.</span><span class="sxs-lookup"><span data-stu-id="329ff-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="329ff-162">Теперь API проще тестировать.</span><span class="sxs-lookup"><span data-stu-id="329ff-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="329ff-163">Управление ошибками</span><span class="sxs-lookup"><span data-stu-id="329ff-163">Error management</span></span>

<span data-ttu-id="329ff-164">Управление ошибками в больших системах является сложной и устойчивой задачей, и нет ни одного серебристого маркера, обеспечивающего отказоустойчивость и поведение систем.</span><span class="sxs-lookup"><span data-stu-id="329ff-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="329ff-165">Приведенные ниже рекомендации должны содержать рекомендации по переходу на эту трудную область.</span><span class="sxs-lookup"><span data-stu-id="329ff-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="329ff-166">Представляет случаи ошибок и недопустимое состояние в типах, встроенных в ваш домен</span><span class="sxs-lookup"><span data-stu-id="329ff-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="329ff-167">С помощью [размеченных объединений](../language-reference/discriminated-unions.md) F# дает возможность представить состояние неисправной программы в системе типов.</span><span class="sxs-lookup"><span data-stu-id="329ff-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="329ff-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="329ff-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="329ff-169">В этом случае может произойти сбой из-за трех известных способов снятия денег с банковского счета.</span><span class="sxs-lookup"><span data-stu-id="329ff-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="329ff-170">Каждый вариант ошибки представлен в типе и, таким образом, может быть достаточно безопасен во всей программе.</span><span class="sxs-lookup"><span data-stu-id="329ff-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="329ff-171">В общем случае, если вы можете моделировать различные способы **сбоя** в вашем домене, код обработки ошибок больше не обрабатывается в дополнение к обычной последовательности программ.</span><span class="sxs-lookup"><span data-stu-id="329ff-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="329ff-172">Это просто часть обычного потока программы, не признанная **исключительной**.</span><span class="sxs-lookup"><span data-stu-id="329ff-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="329ff-173">Существует два основных преимущества:</span><span class="sxs-lookup"><span data-stu-id="329ff-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="329ff-174">С течением времени мы проще поддерживать изменения в домене.</span><span class="sxs-lookup"><span data-stu-id="329ff-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="329ff-175">Случаи ошибок проще в модульном тесте.</span><span class="sxs-lookup"><span data-stu-id="329ff-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="329ff-176">Использовать исключения, если ошибки не могут быть представлены с помощью типов</span><span class="sxs-lookup"><span data-stu-id="329ff-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="329ff-177">Не все ошибки могут быть представлены в домене проблемы.</span><span class="sxs-lookup"><span data-stu-id="329ff-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="329ff-178">Эти типы ошибок являются *исключительными* по своей природе, поэтому возможность вызывать и перехватывать исключения в F#.</span><span class="sxs-lookup"><span data-stu-id="329ff-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="329ff-179">Во-первых, рекомендуется ознакомиться с [рекомендациями по проектированию исключений](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="329ff-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="329ff-180">Они также применимы к F#.</span><span class="sxs-lookup"><span data-stu-id="329ff-180">These are also applicable to F#.</span></span>

<span data-ttu-id="329ff-181">Основные конструкции, доступные в, F# в целях создания исключений следует учитывать в следующем порядке предпочтения:</span><span class="sxs-lookup"><span data-stu-id="329ff-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="329ff-182">Функция</span><span class="sxs-lookup"><span data-stu-id="329ff-182">Function</span></span> | <span data-ttu-id="329ff-183">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="329ff-183">Syntax</span></span> | <span data-ttu-id="329ff-184">Цель</span><span class="sxs-lookup"><span data-stu-id="329ff-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="329ff-185">Вызывает `System.ArgumentNullException` с указанным именем аргумента.</span><span class="sxs-lookup"><span data-stu-id="329ff-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="329ff-186">Вызывает `System.ArgumentException` с указанным именем аргумента и сообщением.</span><span class="sxs-lookup"><span data-stu-id="329ff-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="329ff-187">Вызывает `System.InvalidOperationException` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="329ff-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="329ff-188">Универсальный механизм для генерации исключений.</span><span class="sxs-lookup"><span data-stu-id="329ff-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="329ff-189">Вызывает `System.Exception` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="329ff-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="329ff-190">Вызывает `System.Exception` с сообщением, определяемым строкой формата и его входными данными.</span><span class="sxs-lookup"><span data-stu-id="329ff-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="329ff-191">Используйте `nullArg`, `invalidArg` и `invalidOp` в качестве механизма вызова `ArgumentNullException`, `ArgumentException` и `InvalidOperationException`, если это уместно.</span><span class="sxs-lookup"><span data-stu-id="329ff-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="329ff-192">Обычно следует избегать функций `failwith` и `failwithf`, поскольку они создают базовый тип `Exception`, а не определенное исключение.</span><span class="sxs-lookup"><span data-stu-id="329ff-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="329ff-193">В соответствии с [рекомендациями по проектированию исключений](../../standard/design-guidelines/exceptions.md), когда это возможно, необходимо вызвать более конкретные исключения.</span><span class="sxs-lookup"><span data-stu-id="329ff-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="329ff-194">Использование синтаксиса обработки исключений</span><span class="sxs-lookup"><span data-stu-id="329ff-194">Using exception-handling syntax</span></span>

<span data-ttu-id="329ff-195">F#поддерживает шаблоны исключений с помощью синтаксиса`try...with`:</span><span class="sxs-lookup"><span data-stu-id="329ff-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="329ff-196">Согласование функций, выполняемых в случае исключения с сопоставлением шаблонов, может быть немного сложным, если вы хотите оставить код нечетким.</span><span class="sxs-lookup"><span data-stu-id="329ff-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="329ff-197">Одним из способов обработки этого является использование [активных шаблонов](../language-reference/active-patterns.md) в качестве средства для группирования функциональности, окружающей ошибку, с самим исключением.</span><span class="sxs-lookup"><span data-stu-id="329ff-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="329ff-198">Например, вы можете использовать API, который, когда он создает исключение, заключает в метаданные исключения ценную информацию.</span><span class="sxs-lookup"><span data-stu-id="329ff-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="329ff-199">Распаковка полезного значения в тексте перехваченного исключения в активном шаблоне и возвращение этого значения может оказаться полезной в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="329ff-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="329ff-200">Не используйте собственную обработку ошибок для замены исключений</span><span class="sxs-lookup"><span data-stu-id="329ff-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="329ff-201">Исключения рассматриваются как несколько табу в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="329ff-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="329ff-202">Действительно, исключения нарушают чистоту, поэтому их можно спокойно считать недостаточной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="329ff-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="329ff-203">Однако это пропускает реальность, где должен выполняться код, и могут возникнуть ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="329ff-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="329ff-204">Как правило, написание кода предполагает, что большинство вещей не являются ни чистым, ни итоговым, чтобы максимально упростить неприятные сюрпризы.</span><span class="sxs-lookup"><span data-stu-id="329ff-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="329ff-205">Важно учитывать следующие основные сильные стороны и аспекты исключений в отношении их релевантности и адекватности в среде выполнения .NET и многоязыковой экосистемы в целом:</span><span class="sxs-lookup"><span data-stu-id="329ff-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="329ff-206">Они содержат подробные диагностические сведения, которые очень полезны при отладке проблемы.</span><span class="sxs-lookup"><span data-stu-id="329ff-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="329ff-207">Они хорошо понятны среде выполнения и другим языкам .NET.</span><span class="sxs-lookup"><span data-stu-id="329ff-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="329ff-208">Они могут уменьшить значительный шаблон при сравнении с кодом, который *не позволяет избежать* исключений, путем реализации некоторого подмножества их семантики на произвольной основе.</span><span class="sxs-lookup"><span data-stu-id="329ff-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="329ff-209">Этот третий момент является критически важным.</span><span class="sxs-lookup"><span data-stu-id="329ff-209">This third point is critical.</span></span> <span data-ttu-id="329ff-210">Для нетривиальных сложных операций невозможность использования исключений может привести к работе с такими структурами:</span><span class="sxs-lookup"><span data-stu-id="329ff-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="329ff-211">Что может легко привести к ненадежному коду, такому как сопоставление шаблонов при ошибках со строковыми типами:</span><span class="sxs-lookup"><span data-stu-id="329ff-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="329ff-212">Кроме того, может возникнуть желание проглотить любое исключение в случае, если для "простой" функции возвращается тип "лучше":</span><span class="sxs-lookup"><span data-stu-id="329ff-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="329ff-213">К сожалению, `tryReadAllText` может вызывать многочисленные исключения в зависимости от множества вещей, которые могут произойти в файловой системе, и этот код отклоняет любые сведения о том, что в вашей среде может быть неверно.</span><span class="sxs-lookup"><span data-stu-id="329ff-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="329ff-214">Если заменить этот код типом результата, то будет выполнен синтаксический анализ сообщения об ошибке с вводом строкового типа:</span><span class="sxs-lookup"><span data-stu-id="329ff-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="329ff-215">И размещение объекта исключения в конструкторе `Error` просто заставляет вас правильно работать с типом исключения в месте вызова, а не в функции.</span><span class="sxs-lookup"><span data-stu-id="329ff-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="329ff-216">Это позволяет эффективно создавать проверенные исключения, которые, в свою унфун, могут работать как вызывающий объект API.</span><span class="sxs-lookup"><span data-stu-id="329ff-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="329ff-217">Хорошим альтернативой приведенным выше примерам является перехват *конкретных* исключений и возврат осмысленного значения в контексте этого исключения.</span><span class="sxs-lookup"><span data-stu-id="329ff-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="329ff-218">Если изменить функцию `tryReadAllText` следующим образом, `None` имеет большее значение:</span><span class="sxs-lookup"><span data-stu-id="329ff-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="329ff-219">Вместо того, чтобы работать в качестве блока catch-all, эта функция теперь будет правильно обработана, если файл не найден и присвоить это значение возвращаемому значению.</span><span class="sxs-lookup"><span data-stu-id="329ff-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="329ff-220">Это возвращаемое значение может сопоставляться с этим случаем ошибки, не удаляя никаких контекстных сведений и не требуя от вызывающих объектов обращения к ситуации, которая может не быть актуальной в этой точке кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="329ff-221">Типы, такие как `Result<'Success, 'Error>`, подходят для основных операций, в которых они не F# являются вложенными, а необязательные типы идеально подходят для представления, когда что-либо может вернуть *что* -либо или *ничего*.</span><span class="sxs-lookup"><span data-stu-id="329ff-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="329ff-222">Однако они не являются заменой для исключений и не должны использоваться при попытке заменить исключения.</span><span class="sxs-lookup"><span data-stu-id="329ff-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="329ff-223">Вместо этого их следует применять внимательно, чтобы решить определенные аспекты политики исключений и управления ошибками.</span><span class="sxs-lookup"><span data-stu-id="329ff-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="329ff-224">Частичное программирование приложений и без точек</span><span class="sxs-lookup"><span data-stu-id="329ff-224">Partial application and point-free programming</span></span>

<span data-ttu-id="329ff-225">F#поддерживает частичное применение приложений и, таким образом, различные способы программирования в стиле "без точки".</span><span class="sxs-lookup"><span data-stu-id="329ff-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="329ff-226">Это может быть полезно для повторного использования кода в модуле или реализации чего-либо, но обычно не является каким-либо общедоступным.</span><span class="sxs-lookup"><span data-stu-id="329ff-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="329ff-227">Как правило, программирование без точки зрения не является приростом самого себя и может добавить значительный захватывающий барьер для людей, не вошедших в стиль.</span><span class="sxs-lookup"><span data-stu-id="329ff-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="329ff-228">Не используйте частичные приложения и карринг в общедоступных API</span><span class="sxs-lookup"><span data-stu-id="329ff-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="329ff-229">При небольшом исключении использование частичного приложения в общедоступных API может вызвать путаницу для потребителей.</span><span class="sxs-lookup"><span data-stu-id="329ff-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="329ff-230">Обычно значения, привязанные к `let`F# в коде, являются **значениями**, а не **значениями функций**.</span><span class="sxs-lookup"><span data-stu-id="329ff-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="329ff-231">Сочетание значений и значений функций может привести к сохранению небольшого числа строк кода в Exchange для довольно большого количества системных издержек, особенно в сочетании с операторами, такими как `>>` для создания функций.</span><span class="sxs-lookup"><span data-stu-id="329ff-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="329ff-232">Примите во внимание особенности разработки средств для программирования без точки зрения</span><span class="sxs-lookup"><span data-stu-id="329ff-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="329ff-233">Каррированных функции не помечают свои аргументы.</span><span class="sxs-lookup"><span data-stu-id="329ff-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="329ff-234">Это влияет на средства.</span><span class="sxs-lookup"><span data-stu-id="329ff-234">This has tooling implications.</span></span> <span data-ttu-id="329ff-235">Рассмотрим следующие две функции:</span><span class="sxs-lookup"><span data-stu-id="329ff-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="329ff-236">Оба являются допустимыми функциями, но `funcWithApplication` является каррированных функцией.</span><span class="sxs-lookup"><span data-stu-id="329ff-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="329ff-237">При наведении указателя мыши на типы в редакторе вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="329ff-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="329ff-238">В месте вызова всплывающие подсказки в инструментарии, такие как Visual Studio, не предоставляют осмысленной информации о том, как фактически представляются типы входных данных `string` и `int`.</span><span class="sxs-lookup"><span data-stu-id="329ff-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="329ff-239">Если вы столкнулись с кодом без точки, например `funcWithApplication`, который является общедоступным, рекомендуется выполнить полное расширение η, чтобы средства могли получать осмысленные имена для аргументов.</span><span class="sxs-lookup"><span data-stu-id="329ff-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="329ff-240">Кроме того, код без поддержки точек отладки может быть непростым, если это невозможно.</span><span class="sxs-lookup"><span data-stu-id="329ff-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="329ff-241">Средства отладки зависят от значений, привязанных к именам (например, `let` привязок), чтобы можно было проверять промежуточные значения в середине по исполнению.</span><span class="sxs-lookup"><span data-stu-id="329ff-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="329ff-242">Если код не имеет значений для проверки, отладка не требуется.</span><span class="sxs-lookup"><span data-stu-id="329ff-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="329ff-243">В будущем средства отладки могут развиваться для синтезирования этих значений с учетом ранее выполненных путей, но не рекомендуется хеджирование свои элементы на *потенциальные* функции отладки.</span><span class="sxs-lookup"><span data-stu-id="329ff-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="329ff-244">Рассмотрите частичные приложения как методику сокращения внутреннего стандартного</span><span class="sxs-lookup"><span data-stu-id="329ff-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="329ff-245">В отличие от предыдущей точки, частичное применение — это замечательное средство для сокращения стандартного в приложении или более глубоких внутренних компонентов API.</span><span class="sxs-lookup"><span data-stu-id="329ff-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="329ff-246">Он может быть полезен для модульного тестирования реализации более сложных интерфейсов API, где часто возникает проблема с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="329ff-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="329ff-247">Например, в следующем коде показано, как можно добиться того, что большинство инфраструктурных макетов позволит вам не брать внешнюю зависимость от такой платформы, а также изучать связанный API-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="329ff-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="329ff-248">Например, рассмотрим следующее решение топографии:</span><span class="sxs-lookup"><span data-stu-id="329ff-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="329ff-249">`ImplementationLogic.fsproj` может представлять код, например:</span><span class="sxs-lookup"><span data-stu-id="329ff-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="329ff-250">Модульное тестирование `Transactions.doTransaction` в `ImplementationLogic.Tests.fsproj` — это просто:</span><span class="sxs-lookup"><span data-stu-id="329ff-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="329ff-251">Частичное применение `doTransaction` с объектом контекста макетирования позволяет вызывать функцию во всех модульных тестах, не требуя каждый раз создавать макет макета.</span><span class="sxs-lookup"><span data-stu-id="329ff-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="329ff-252">Этот метод не должен применяться к всей базе кода в универсальном коде, но это хороший способ сокращения стандартного для сложных внутренних компонентов и модульного тестирования этих внутренних компонентов.</span><span class="sxs-lookup"><span data-stu-id="329ff-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="329ff-253">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="329ff-253">Access control</span></span>

<span data-ttu-id="329ff-254">F#имеет несколько параметров для [управления доступом](../language-reference/access-control.md), наследуемых от доступных в среде выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="329ff-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="329ff-255">Они не просто могут использоваться для типов. их также можно использовать для функций.</span><span class="sxs-lookup"><span data-stu-id="329ff-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="329ff-256">Предпочитать типы и члены, не относящиеся к`public`, до тех пор, пока они не понадобятся для общего использования.</span><span class="sxs-lookup"><span data-stu-id="329ff-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="329ff-257">Это также сводится к уменьшению числа потребителей, с которыми связана пара.</span><span class="sxs-lookup"><span data-stu-id="329ff-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="329ff-258">Оставайтесь в курсе всех вспомогательных функций `private`.</span><span class="sxs-lookup"><span data-stu-id="329ff-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="329ff-259">Рекомендуется использовать `[<AutoOpen>]` в частном модуле вспомогательных функций, если они становятся многочисленными.</span><span class="sxs-lookup"><span data-stu-id="329ff-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="329ff-260">Определение типа и универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="329ff-260">Type inference and generics</span></span>

<span data-ttu-id="329ff-261">Определение типа может помочь вам в вводе большого числа шаблонов.</span><span class="sxs-lookup"><span data-stu-id="329ff-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="329ff-262">И автоматическое обобщение в F# компиляторе может помочь в написании более универсального кода с практически без дополнительных усилий.</span><span class="sxs-lookup"><span data-stu-id="329ff-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="329ff-263">Однако эти функции не являются универсальными.</span><span class="sxs-lookup"><span data-stu-id="329ff-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="329ff-264">Рекомендуется помечать имена аргументов явными типами в общедоступных API и не полагаться на вывод типа для этого.</span><span class="sxs-lookup"><span data-stu-id="329ff-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="329ff-265">Причина в том, что **вы** должны контролировать форму API, а не компилятор.</span><span class="sxs-lookup"><span data-stu-id="329ff-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="329ff-266">Несмотря на то, что компилятор может выполнять хорошее задание в выведение типов, можно изменить форму API, если внутренние компоненты, от которых он зависит, изменили типы.</span><span class="sxs-lookup"><span data-stu-id="329ff-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="329ff-267">Это может быть то, что вам нужно, но это почти наверняка приведет к прерыванию изменения API, с которым потом нижестоящим потребителям придется справиться.</span><span class="sxs-lookup"><span data-stu-id="329ff-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="329ff-268">Вместо этого, если вы явно управляете формой открытого API, вы можете управлять этими критическими изменениями.</span><span class="sxs-lookup"><span data-stu-id="329ff-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="329ff-269">В терминах DDD это можно рассматривать как уровень защиты от повреждений.</span><span class="sxs-lookup"><span data-stu-id="329ff-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="329ff-270">Рекомендуется дать универсальным аргументам понятное имя.</span><span class="sxs-lookup"><span data-stu-id="329ff-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="329ff-271">Если вы не пишете действительно универсальный код, который не относится к конкретному домену, понятное имя может помочь другим программистам понять, в каком домене они работают.</span><span class="sxs-lookup"><span data-stu-id="329ff-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="329ff-272">Например, параметр типа с именем `'Document` в контексте взаимодействия с базой данных документов делает более ясно, что универсальные типы документов могут быть приняты функцией или членом, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="329ff-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="329ff-273">Рассмотрите возможность именования параметров универсального типа с помощью PascalCase.</span><span class="sxs-lookup"><span data-stu-id="329ff-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="329ff-274">Это общий способ выполнить действия в .NET, поэтому рекомендуется использовать PascalCase, а не snake_case или camelCase.</span><span class="sxs-lookup"><span data-stu-id="329ff-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="329ff-275">Наконец, автоматическое обобщение не всегда является boonом для тех, кто не является F# новым в или большой базе кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="329ff-276">При использовании универсальных компонентов существуют накладные расходы на переприятие.</span><span class="sxs-lookup"><span data-stu-id="329ff-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="329ff-277">Более того, если автоматически обобщенные функции не используются с различными типами входных данных (то есть если они предназначены для использования), то в этот момент времени не существует реальных преимуществ.</span><span class="sxs-lookup"><span data-stu-id="329ff-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="329ff-278">Всегда учитывайте, что код, который вы пишете, будет действительно выгодным.</span><span class="sxs-lookup"><span data-stu-id="329ff-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="329ff-279">Производительность</span><span class="sxs-lookup"><span data-stu-id="329ff-279">Performance</span></span>

<span data-ttu-id="329ff-280">F#значения по умолчанию являются неизменяемыми, что позволяет избежать определенных классов ошибок (особенно связанных с параллелизмом и параллелизмом).</span><span class="sxs-lookup"><span data-stu-id="329ff-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="329ff-281">Однако в некоторых случаях, чтобы достичь оптимальной (или даже разумной) эффективности времени выполнения или выделения памяти, объем работы можно реализовать с помощью изменения состояния на месте.</span><span class="sxs-lookup"><span data-stu-id="329ff-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="329ff-282">Это можно сделать F# с помощью ключевого слова`mutable`.</span><span class="sxs-lookup"><span data-stu-id="329ff-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="329ff-283">Однако использование `mutable` в F# может быть, скорее всего, с функциональной чистотой.</span><span class="sxs-lookup"><span data-stu-id="329ff-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="329ff-284">Это нормально, если вы настраиваете ожидания от чистоты до [ссылочной прозрачности](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="329ff-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="329ff-285">Ссылочная прозрачность — не чистота — конечная цель при F# написании функций.</span><span class="sxs-lookup"><span data-stu-id="329ff-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="329ff-286">Это позволяет написать функциональный интерфейс с реализацией на основе изменений для критичного в производительности кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="329ff-287">Перенос изменяемого кода в неизменяемые интерфейсы</span><span class="sxs-lookup"><span data-stu-id="329ff-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="329ff-288">При использовании ссылочной прозрачности в качестве цели очень важно написать код, который не предоставляет изменяемую ненужные функции, критические для производительности.</span><span class="sxs-lookup"><span data-stu-id="329ff-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="329ff-289">Например, следующий код реализует функцию `Array.contains` в F# основной библиотеке:</span><span class="sxs-lookup"><span data-stu-id="329ff-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="329ff-290">Многократное обращение к этой функции не приводит к изменению базового массива, а также не требует поддержки какого либо изменяющегося состояния при его использовании.</span><span class="sxs-lookup"><span data-stu-id="329ff-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="329ff-291">Эта функция прозрачна, даже если в ней почти каждая строка кода использует изменения.</span><span class="sxs-lookup"><span data-stu-id="329ff-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="329ff-292">Рассмотрите возможность инкапсуляции изменяемых данных в классы</span><span class="sxs-lookup"><span data-stu-id="329ff-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="329ff-293">В предыдущем примере использовалась одна функция для инкапсуляции операций с использованием изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="329ff-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="329ff-294">Это не всегда достаточно для более сложных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="329ff-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="329ff-295">Рассмотрим следующие наборы функций:</span><span class="sxs-lookup"><span data-stu-id="329ff-295">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="329ff-296">Этот код является выполняемым, но он предоставляет структуру данных на основе изменений, которые вызывающие объекты отвечают за обслуживание.</span><span class="sxs-lookup"><span data-stu-id="329ff-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="329ff-297">Это можно обернуть внутри класса без базовых членов, которые могут измениться:</span><span class="sxs-lookup"><span data-stu-id="329ff-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="329ff-298">`Closure1Table` инкапсулирует базовую структуру данных на основе изменений, тем самым не представляя вызывающие объекты поддерживать базовую структуру данных.</span><span class="sxs-lookup"><span data-stu-id="329ff-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="329ff-299">Классы — это мощный способ инкапсуляции данных и подпрограмм, основанных на возможностях, без предоставления сведений вызывающим объектам.</span><span class="sxs-lookup"><span data-stu-id="329ff-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="329ff-300">Предпочитать `let mutable` для ссылок на ячейки</span><span class="sxs-lookup"><span data-stu-id="329ff-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="329ff-301">Ссылочные ячейки — это способ представления ссылки на значение, а не само значение.</span><span class="sxs-lookup"><span data-stu-id="329ff-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="329ff-302">Хотя они могут использоваться для критичного в производительности кода, они обычно не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="329ff-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="329ff-303">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="329ff-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="329ff-304">Использование ссылочной ячейки теперь «засоряет» все последующие коды с целью разыменования и повторной ссылки на базовые данные.</span><span class="sxs-lookup"><span data-stu-id="329ff-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="329ff-305">Вместо этого рассмотрите `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="329ff-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="329ff-306">Помимо единственной точки изменения в середине лямбда-выражения, весь остальной код, который касается `acc`, может сделать это так, что не отличается от использования обычного неизменяемого значения, привязанного к `let`.</span><span class="sxs-lookup"><span data-stu-id="329ff-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="329ff-307">Это упростит изменение со временем.</span><span class="sxs-lookup"><span data-stu-id="329ff-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="329ff-308">Программирование объектов</span><span class="sxs-lookup"><span data-stu-id="329ff-308">Object programming</span></span>

<span data-ttu-id="329ff-309">F#обеспечивает полную поддержку объектов и объектно-ориентированных концепций (ОО).</span><span class="sxs-lookup"><span data-stu-id="329ff-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="329ff-310">Хотя многие основные понятия ОО являются мощными и полезными, не все из них идеально подходят для использования.</span><span class="sxs-lookup"><span data-stu-id="329ff-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="329ff-311">В следующих списках приведены рекомендации по категориям функций ОО на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="329ff-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="329ff-312">**Рассмотрите возможность использования этих функций во многих ситуациях.**</span><span class="sxs-lookup"><span data-stu-id="329ff-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="329ff-313">Точечная нотация (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="329ff-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="329ff-314">Члены экземпляра</span><span class="sxs-lookup"><span data-stu-id="329ff-314">Instance members</span></span>
* <span data-ttu-id="329ff-315">Неявные конструкторы</span><span class="sxs-lookup"><span data-stu-id="329ff-315">Implicit constructors</span></span>
* <span data-ttu-id="329ff-316">Статические члены</span><span class="sxs-lookup"><span data-stu-id="329ff-316">Static members</span></span>
* <span data-ttu-id="329ff-317">Нотация индексатора (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="329ff-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="329ff-318">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="329ff-318">Named and Optional arguments</span></span>
* <span data-ttu-id="329ff-319">Реализации интерфейсов и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="329ff-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="329ff-320">**Не обращайтесь к этим функциям первыми, но применяйте их разумным образом, когда они удобны для решения проблемы:**</span><span class="sxs-lookup"><span data-stu-id="329ff-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="329ff-321">Перегрузка методов</span><span class="sxs-lookup"><span data-stu-id="329ff-321">Method overloading</span></span>
* <span data-ttu-id="329ff-322">Инкапсулированные изменяемые данные</span><span class="sxs-lookup"><span data-stu-id="329ff-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="329ff-323">Операторы в типах</span><span class="sxs-lookup"><span data-stu-id="329ff-323">Operators on types</span></span>
* <span data-ttu-id="329ff-324">Автоматические свойства</span><span class="sxs-lookup"><span data-stu-id="329ff-324">Auto properties</span></span>
* <span data-ttu-id="329ff-325">Реализация `IDisposable` и `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="329ff-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="329ff-326">Расширения типов</span><span class="sxs-lookup"><span data-stu-id="329ff-326">Type extensions</span></span>
* <span data-ttu-id="329ff-327">события</span><span class="sxs-lookup"><span data-stu-id="329ff-327">Events</span></span>
* <span data-ttu-id="329ff-328">структурам;</span><span class="sxs-lookup"><span data-stu-id="329ff-328">Structs</span></span>
* <span data-ttu-id="329ff-329">Делегаты</span><span class="sxs-lookup"><span data-stu-id="329ff-329">Delegates</span></span>
* <span data-ttu-id="329ff-330">перечислениям;</span><span class="sxs-lookup"><span data-stu-id="329ff-330">Enums</span></span>

<span data-ttu-id="329ff-331">**Как правило, Избегайте этих функций, если их не нужно использовать:**</span><span class="sxs-lookup"><span data-stu-id="329ff-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="329ff-332">Иерархии типов на основе наследования и наследование реализации</span><span class="sxs-lookup"><span data-stu-id="329ff-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="329ff-333">Значения NULL и `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="329ff-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="329ff-334">Предпочитать композицию наследования</span><span class="sxs-lookup"><span data-stu-id="329ff-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="329ff-335">[Композиция с наследованием](https://en.wikipedia.org/wiki/Composition_over_inheritance) — это долгий идиом, который F# может придерживаться хорошего кода.</span><span class="sxs-lookup"><span data-stu-id="329ff-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="329ff-336">Основной принцип заключается в том, что не следует предоставлять базовый класс и заставить вызывающие объекты наследовать от этого базового класса для получения функциональности.</span><span class="sxs-lookup"><span data-stu-id="329ff-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="329ff-337">Использование выражений объектов для реализации интерфейсов, если не требуется класс</span><span class="sxs-lookup"><span data-stu-id="329ff-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="329ff-338">[Выражения объектов](../language-reference/object-expressions.md) позволяют реализовать интерфейсы на лету, привязывая реализованный интерфейс к значению без необходимости делать это внутри класса.</span><span class="sxs-lookup"><span data-stu-id="329ff-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="329ff-339">Это удобно, особенно если требуется _только_ реализовать интерфейс и не требуется полный класс.</span><span class="sxs-lookup"><span data-stu-id="329ff-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="329ff-340">Например, ниже приведен код, который выполняется в [Ionide](http://ionide.io/) для предоставления действия по исправлению кода, если вы добавили символ, для которого у вас нет оператора `open`:</span><span class="sxs-lookup"><span data-stu-id="329ff-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="329ff-341">Поскольку при взаимодействии с Visual Studio Code API не требуется класс, выражения объектов являются идеальным средством для этого.</span><span class="sxs-lookup"><span data-stu-id="329ff-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="329ff-342">Они также полезны при модульном тестировании, когда необходимо создать заглушку интерфейса с помощью подпрограмм тестирования нерегламентированным способом.</span><span class="sxs-lookup"><span data-stu-id="329ff-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="329ff-343">Рекомендуется использовать сокращения типов для сокращения сигнатур</span><span class="sxs-lookup"><span data-stu-id="329ff-343">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="329ff-344">[Аббревиатуры типов](../language-reference/type-abbreviations.md) — это удобный способ назначения метки другому типу, например сигнатуре функции или более сложному типу.</span><span class="sxs-lookup"><span data-stu-id="329ff-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="329ff-345">Например, следующий псевдоним назначает метку, необходимую для определения вычислений с помощью [CNTK](https://docs.microsoft.com/cognitive-toolkit/), библиотеки глубокого обучения:</span><span class="sxs-lookup"><span data-stu-id="329ff-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="329ff-346">Имя `Computation` — это удобный способ обозначить любую функцию, совпадающую с сигнатурой, которая является псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="329ff-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="329ff-347">Использование сокращенных обоподобие типов удобно и позволяет использовать более сжатый код.</span><span class="sxs-lookup"><span data-stu-id="329ff-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="329ff-348">Избегайте использования сокращений типов для представления домена</span><span class="sxs-lookup"><span data-stu-id="329ff-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="329ff-349">Хотя аббревиатуры типов удобно использовать для присвоения имени сигнатурам функций, они могут вызывать путаницу, если аббревиатинг другие типы.</span><span class="sxs-lookup"><span data-stu-id="329ff-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="329ff-350">Рассмотрим следующее сокращение:</span><span class="sxs-lookup"><span data-stu-id="329ff-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="329ff-351">Это может быть затруднено несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="329ff-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="329ff-352">`BufferSize` не является абстракцией; Это просто другое имя для целого числа.</span><span class="sxs-lookup"><span data-stu-id="329ff-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="329ff-353">Если `BufferSize` предоставляется в общедоступном API, он легко интерпретируется как неправильное, что означает не только `int`.</span><span class="sxs-lookup"><span data-stu-id="329ff-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="329ff-354">Как правило, типы домена имеют несколько атрибутов и не являются примитивными типами, такими как `int`.</span><span class="sxs-lookup"><span data-stu-id="329ff-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="329ff-355">Это сокращение нарушает это допущение.</span><span class="sxs-lookup"><span data-stu-id="329ff-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="329ff-356">Регистр `BufferSize` (PascalCase) подразумевает, что этот тип содержит больше данных.</span><span class="sxs-lookup"><span data-stu-id="329ff-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="329ff-357">Этот псевдоним не обеспечивает повышенную четкость по сравнению с предоставлением именованного аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="329ff-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="329ff-358">Аббревиатура не будет сокомпилироваться в скомпилированном IL; Это всего лишь целое число, а этот псевдоним является конструкцией времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="329ff-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="329ff-359">В целом, ловушки с сокращениями типов заключаются в том, что они **не** являются абстракциями для типов, которые они аббревиатинг.</span><span class="sxs-lookup"><span data-stu-id="329ff-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="329ff-360">В предыдущем примере `BufferSize` — это просто `int`, который не содержит дополнительных данных, а также любые преимущества системы типов, Кроме того, что `int` уже есть.</span><span class="sxs-lookup"><span data-stu-id="329ff-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="329ff-361">Альтернативный подход к использованию сокращений типов для представления домена — Использование размеченных объединений с одним вариантом.</span><span class="sxs-lookup"><span data-stu-id="329ff-361">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="329ff-362">Предыдущий пример можно смоделировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="329ff-362">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="329ff-363">При написании кода, который работает в терминах `BufferSize` и его базовом значении, необходимо создать один из них вместо передачи любого произвольного целого числа:</span><span class="sxs-lookup"><span data-stu-id="329ff-363">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="329ff-364">Это уменьшает вероятность ошибочного перепередачи произвольного целого числа в функцию `send`, так как вызывающий объект должен создать `BufferSize` тип для заключения значения перед вызовом функции.</span><span class="sxs-lookup"><span data-stu-id="329ff-364">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
