---
title: 'Соглашения о написании кода на языке F #'
description: 'Дополнительные сведения, общие рекомендации и идиом при написании кода F #.'
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="f-coding-conventions"></a><span data-ttu-id="2911e-103">Соглашения о написании кода на языке F #</span><span class="sxs-lookup"><span data-stu-id="2911e-103">F# coding conventions</span></span>

<span data-ttu-id="2911e-104">Из опыта работы с большой F # формулируются следующим соглашениям базы кода.</span><span class="sxs-lookup"><span data-stu-id="2911e-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="2911e-105">[Пять принципов хороший код F #](index.md#five-principles-of-good-f-code) являются основой каждой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="2911e-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="2911e-106">Они связаны с [рекомендации по проектированию компонент F #](component-design-guidelines.md), но подходят для любого кода F #, не только компонентов, таких как библиотеки.</span><span class="sxs-lookup"><span data-stu-id="2911e-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="2911e-107">Организация кода</span><span class="sxs-lookup"><span data-stu-id="2911e-107">Organizing code</span></span>

<span data-ttu-id="2911e-108">Возможности два основных способа организации кода F #: модули и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2911e-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="2911e-109">Они похожи, но имеют следующие отличия:</span><span class="sxs-lookup"><span data-stu-id="2911e-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="2911e-110">Пространства имен, компилируются как пространства имен .NET.</span><span class="sxs-lookup"><span data-stu-id="2911e-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="2911e-111">Модули компилируются как статические классы.</span><span class="sxs-lookup"><span data-stu-id="2911e-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="2911e-112">Пространства имен всегда являются верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="2911e-112">Namespaces are always top level.</span></span> <span data-ttu-id="2911e-113">Модули могут быть верхнего уровня и вложенными в других модулях.</span><span class="sxs-lookup"><span data-stu-id="2911e-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="2911e-114">Пространства имен могут охватывать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="2911e-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="2911e-115">Модули не могут.</span><span class="sxs-lookup"><span data-stu-id="2911e-115">Modules cannot.</span></span>
* <span data-ttu-id="2911e-116">Можно снабдить модули `[<RequireQualifiedAccess>]` и `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="2911e-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="2911e-117">Следующие рекомендации помогут использовать их для организации кода.</span><span class="sxs-lookup"><span data-stu-id="2911e-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="2911e-118">Предпочтение пространства имен на верхнем уровне</span><span class="sxs-lookup"><span data-stu-id="2911e-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="2911e-119">Для любого общедоступной кода пространства имен являются предпочтительным модули верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="2911e-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="2911e-120">Так, как они компилируются как пространства имен .NET, они могут использоваться из C# с не возникает проблем.</span><span class="sxs-lookup"><span data-stu-id="2911e-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="2911e-121">С помощью модуля верхнего уровня не могут отображаться различные при вызове только из F #, но для C# потребителей, вызывающие объекты могут удивить необходимости квалификации `MyClass` с `MyCode` модуля.</span><span class="sxs-lookup"><span data-stu-id="2911e-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="2911e-122">Тщательно применить `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="2911e-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="2911e-123">`[<AutoOpen>]` Конструкция можно повредить области Доступные вызывающим объектам и ответ на что-то откуда «magic».</span><span class="sxs-lookup"><span data-stu-id="2911e-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="2911e-124">Это обычно не хорошо.</span><span class="sxs-lookup"><span data-stu-id="2911e-124">This is generally not a good thing.</span></span> <span data-ttu-id="2911e-125">Исключением из этого правила является основной библиотеки F #, сам (хотя этот факт также немного противоречивым).</span><span class="sxs-lookup"><span data-stu-id="2911e-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="2911e-126">Однако это удобный метод при наличии модуля поддержки для открытого API-интерфейса, которую нужно организовать отдельно от, открытый API.</span><span class="sxs-lookup"><span data-stu-id="2911e-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="2911e-127">Это позволяет вам четко отдельные реализации из открытого API-интерфейса функции без необходимости каждый раз при вызове его полного определения вспомогательного класса.</span><span class="sxs-lookup"><span data-stu-id="2911e-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="2911e-128">Кроме того, предоставление доступа к методам расширения и построители выражений на уровне пространства имен могут аккуратно выражаться с помощью `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="2911e-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="2911e-129">Используйте `[<RequireQualifiedAccess>]` каждый раз, когда это может вызвать конфликт имен, или вы считаете, что оно помогает обеспечивать читаемость</span><span class="sxs-lookup"><span data-stu-id="2911e-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="2911e-130">Добавление `[<RequireQualifiedAccess>]` атрибут для модуля указывает, что модуль не может быть открыт, и необходимость явной ссылки на элементы модуля полное доступ.</span><span class="sxs-lookup"><span data-stu-id="2911e-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="2911e-131">Например `Microsoft.FSharp.Collections.List` модуль имеет этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="2911e-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="2911e-132">Это полезно в том случае, когда функции и значения в модуле имеют имена, которые могут вступать в конфликт с именами в других модулях.</span><span class="sxs-lookup"><span data-stu-id="2911e-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="2911e-133">Требование полного доступа может значительно повысить удобство поддержки долгосрочной и evolvability библиотеки.</span><span class="sxs-lookup"><span data-stu-id="2911e-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="2911e-134">Сортировка `open` инструкции топологически</span><span class="sxs-lookup"><span data-stu-id="2911e-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="2911e-135">В языке F # порядок объявления имеет значение, в том числе с `open` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2911e-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="2911e-136">В отличие от C#, где эффект `using` и `using static` не зависит от порядка этих инструкций в файле.</span><span class="sxs-lookup"><span data-stu-id="2911e-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="2911e-137">В F # открывается в область видимости элементов можно скрывать другие уже присутствует.</span><span class="sxs-lookup"><span data-stu-id="2911e-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="2911e-138">Это означает, что переупорядочение `open` инструкций может изменить значение кода.</span><span class="sxs-lookup"><span data-stu-id="2911e-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="2911e-139">Таким образом, любые произвольные сортировки всех `open` инструкций (например, алфавитно-цифровом порядке) обычно не рекомендуется, иначе создать другое поведение, которое могут рассчитывать.</span><span class="sxs-lookup"><span data-stu-id="2911e-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="2911e-140">Вместо этого рекомендуется их сортировки [топологически](https://en.wikipedia.org/wiki/Topological_sorting); то есть порядок вашей `open` операторов в порядке, в котором _слои_ определенные системой.</span><span class="sxs-lookup"><span data-stu-id="2911e-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="2911e-141">Это буквенно-цифровой сортировки в разных слоев топологические может также считаться.</span><span class="sxs-lookup"><span data-stu-id="2911e-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="2911e-142">Например вот топологические сортировки для языка F # компилятора открытый API файла службы.</span><span class="sxs-lookup"><span data-stu-id="2911e-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="2911e-143">Обратите внимание, что разрыв строки отделяет топологические слои с каждым слоем сортируемых алфавитно-цифровом порядке после.</span><span class="sxs-lookup"><span data-stu-id="2911e-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="2911e-144">Это верно организует кода без случайно затенение значения.</span><span class="sxs-lookup"><span data-stu-id="2911e-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="2911e-145">Использование классов для содержат значения, которые имеют побочные эффекты</span><span class="sxs-lookup"><span data-stu-id="2911e-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="2911e-146">Существует много раз, при инициализации значение может иметь побочные эффекты, например при создании экземпляра контекста базы данных или другого удаленного ресурса.</span><span class="sxs-lookup"><span data-stu-id="2911e-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="2911e-147">Это заманчивой для инициализации таких сведений в модуль и использовать его в последующих функций:</span><span class="sxs-lookup"><span data-stu-id="2911e-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="2911e-148">Это часто не рекомендуются по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="2911e-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="2911e-149">Во-первых, конфигурацию приложения помещается в базу кода с `dep1` и `dep2`.</span><span class="sxs-lookup"><span data-stu-id="2911e-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="2911e-150">Это довольно трудно поддерживать в больших баз кода.</span><span class="sxs-lookup"><span data-stu-id="2911e-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="2911e-151">Второй, статически инициализированные данных не должно содержать значения, которые не являются потокобезопасными, если компонент себя с помощью нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="2911e-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="2911e-152">Четко нарушено `dep3`.</span><span class="sxs-lookup"><span data-stu-id="2911e-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="2911e-153">Наконец инициализации модуля компилирует в статический конструктор для всего блока компиляции.</span><span class="sxs-lookup"><span data-stu-id="2911e-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="2911e-154">Если возникают ошибки при инициализации значение привязки let в этом модуле, он объявляется в качестве `TypeInitializationException` , сохраняется в кэше в течение всего времени существования приложения.</span><span class="sxs-lookup"><span data-stu-id="2911e-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="2911e-155">Это может быть трудно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="2911e-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="2911e-156">Обычно имеется внутреннее исключение, которое можно попытаться обсуждения, но если нет, то есть не о том, что корневой причиной является.</span><span class="sxs-lookup"><span data-stu-id="2911e-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="2911e-157">Вместо этого используйте только простым классом для хранения зависимости:</span><span class="sxs-lookup"><span data-stu-id="2911e-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="2911e-158">Это позволяет следующее:</span><span class="sxs-lookup"><span data-stu-id="2911e-158">This enables the following:</span></span>

1. <span data-ttu-id="2911e-159">Помещает все зависимые состояния за пределами самого API.</span><span class="sxs-lookup"><span data-stu-id="2911e-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="2911e-160">Настройка теперь может выполняться вне API.</span><span class="sxs-lookup"><span data-stu-id="2911e-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="2911e-161">Ошибки во время инициализации для зависимых значений не предполагается ведут как `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="2911e-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="2911e-162">API-Интерфейс теперь стало проще тестирования.</span><span class="sxs-lookup"><span data-stu-id="2911e-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="2911e-163">Управление обработкой ошибок</span><span class="sxs-lookup"><span data-stu-id="2911e-163">Error management</span></span>

<span data-ttu-id="2911e-164">Управление обработкой ошибок в больших системах является сложной и огромным процесс и существует не silver маркеры в обеспечении системы отказоустойчивые и хорошо работают.</span><span class="sxs-lookup"><span data-stu-id="2911e-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="2911e-165">Следующие рекомендации должны обеспечивать рекомендации при навигации это сложно пространство.</span><span class="sxs-lookup"><span data-stu-id="2911e-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="2911e-166">Представления ошибки и недопустимые состояния в типах, встроенными в домене</span><span class="sxs-lookup"><span data-stu-id="2911e-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="2911e-167">С [размеченные объединения](../language-reference/discriminated-unions.md), F # дает возможность представлять состояние неисправный программы в системе типов.</span><span class="sxs-lookup"><span data-stu-id="2911e-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="2911e-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="2911e-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="2911e-169">В этом случае тремя способами известных которых может произойти сбой снятия денег со банковского счета.</span><span class="sxs-lookup"><span data-stu-id="2911e-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="2911e-170">Каждый случай ошибки представить в типе и может поэтому обрабатываться безопасно в программе.</span><span class="sxs-lookup"><span data-stu-id="2911e-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="2911e-171">Как правило, если можно моделировать различные способы что-то может **ошибкой** данного домена, затем код обработки ошибок больше не рассматривается как что-нибудь должны предусматривать помимо обычных программного потока.</span><span class="sxs-lookup"><span data-stu-id="2911e-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="2911e-172">Он является просто частью нормального выполнения программы и не считается **исключительные**.</span><span class="sxs-lookup"><span data-stu-id="2911e-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="2911e-173">Существует два основных преимущества этого:</span><span class="sxs-lookup"><span data-stu-id="2911e-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="2911e-174">Проще поддерживать при изменении домена.</span><span class="sxs-lookup"><span data-stu-id="2911e-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="2911e-175">Ошибка случаев легче модульного теста.</span><span class="sxs-lookup"><span data-stu-id="2911e-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="2911e-176">Используйте исключения, если ошибки не могут быть представлены с типами</span><span class="sxs-lookup"><span data-stu-id="2911e-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="2911e-177">Не все ошибки могут быть представлены в домене проблему.</span><span class="sxs-lookup"><span data-stu-id="2911e-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="2911e-178">Эти типы ошибок является *исключительные* по своей природе, поэтому возможность вызывать и перехватывать исключения в языке F #.</span><span class="sxs-lookup"><span data-stu-id="2911e-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="2911e-179">Во-первых, рекомендуется ознакомиться с [правила разработки исключений](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2911e-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="2911e-180">Это также применимо к F #.</span><span class="sxs-lookup"><span data-stu-id="2911e-180">These are also applicable to F#.</span></span>

<span data-ttu-id="2911e-181">Основными компонентами, доступные в языке F # в целях возникновения исключений должно рассматриваться в следующем порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="2911e-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="2911e-182">Функция</span><span class="sxs-lookup"><span data-stu-id="2911e-182">Function</span></span> | <span data-ttu-id="2911e-183">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2911e-183">Syntax</span></span> | <span data-ttu-id="2911e-184">Цель</span><span class="sxs-lookup"><span data-stu-id="2911e-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="2911e-185">Вызывает `System.ArgumentNullException` с заданным именем аргумента.</span><span class="sxs-lookup"><span data-stu-id="2911e-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="2911e-186">Вызывает `System.ArgumentException` с заданным именем аргумента и сообщений.</span><span class="sxs-lookup"><span data-stu-id="2911e-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="2911e-187">Вызывает `System.InvalidOperationException` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="2911e-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="2911e-188">Универсальный механизм вызова исключений.</span><span class="sxs-lookup"><span data-stu-id="2911e-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="2911e-189">Вызывает `System.Exception` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="2911e-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="2911e-190">Вызывает `System.Exception` сообщением определяется строка формата и ее входными данными.</span><span class="sxs-lookup"><span data-stu-id="2911e-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="2911e-191">Используйте `nullArg`, `invalidArg` и `invalidOp` в качестве механизма для вызова `ArgumentNullException`, `ArgumentException` и `InvalidOperationException` при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2911e-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="2911e-192">`failwith` И `failwithf` функции обычно следует избегать, так как они вызывают базовый `Exception` тип, не определенное исключение.</span><span class="sxs-lookup"><span data-stu-id="2911e-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="2911e-193">Согласно [правила разработки исключений](../../standard/design-guidelines/exceptions.md), нужно создать более конкретные исключения, если вы можете.</span><span class="sxs-lookup"><span data-stu-id="2911e-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="2911e-194">Используя синтаксис обработки исключений</span><span class="sxs-lookup"><span data-stu-id="2911e-194">Using exception-handling syntax</span></span>

<span data-ttu-id="2911e-195">F # поддерживает шаблоны исключение через `try...with` синтаксис:</span><span class="sxs-lookup"><span data-stu-id="2911e-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="2911e-196">Согласование функциональные возможности для выполнения при возникновении исключения с сопоставлением шаблонов может быть немного сложнее, если вы хотите хранить код очистки.</span><span class="sxs-lookup"><span data-stu-id="2911e-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="2911e-197">Один для обработки этого таким способом является использование [активные шаблоны](../language-reference/active-patterns.md) позволяет вокруг ветвь ошибка с исключением самого функциональность группы.</span><span class="sxs-lookup"><span data-stu-id="2911e-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="2911e-198">Например может использовать API-Интерфейсы, когда он создает исключение, ограничивающий ценную информацию в метаданные исключения.</span><span class="sxs-lookup"><span data-stu-id="2911e-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="2911e-199">Развертывание полезные значение в теле записанного исключения внутри активного шаблона и возвращая значение может быть полезным в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="2911e-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="2911e-200">Не используйте результата вычисления обработку ошибок, чтобы заменить исключения</span><span class="sxs-lookup"><span data-stu-id="2911e-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="2911e-201">Исключения представляются немного запретным в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="2911e-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="2911e-202">На самом деле исключения нарушает чистоты, поэтому можно безопасно рассматривать их работы не совсем.</span><span class="sxs-lookup"><span data-stu-id="2911e-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="2911e-203">Однако это не обрабатывает реальность, где необходимо запустить код, и эту среду выполнения, которые могут возникнуть ошибки.</span><span class="sxs-lookup"><span data-stu-id="2911e-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="2911e-204">В общем случае следует писать код на предположении, что для большинства задач не являются чисто и общее, чтобы свести к минимуму непредсказуемых ситуаций.</span><span class="sxs-lookup"><span data-stu-id="2911e-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="2911e-205">Очень важно учесть следующие основные преимущества/аспекты исключений по отношению к их релевантность и целесообразность в среду выполнения .NET и экосистема версий на разных языках в целом:</span><span class="sxs-lookup"><span data-stu-id="2911e-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="2911e-206">Они содержат подробные диагностические сведения, что очень удобно при отладке проблемы.</span><span class="sxs-lookup"><span data-stu-id="2911e-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="2911e-207">Это хорошо понятны средой выполнения и других языков .NET.</span><span class="sxs-lookup"><span data-stu-id="2911e-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="2911e-208">Позволяют уменьшить значительные стандартного по сравнению с кодом, который выходит за пределы пути *избежать* исключения путем реализации некоторого подмножества их семантика на основе ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="2911e-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="2911e-209">Это третья точка важен.</span><span class="sxs-lookup"><span data-stu-id="2911e-209">This third point is critical.</span></span> <span data-ttu-id="2911e-210">Для нетривиальных сложные операции не сможет использовать исключений может привести работа со структурами следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2911e-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="2911e-211">Который может легко привести к уязвимости кода как «stringly типизированные» ошибки сопоставления шаблонов:</span><span class="sxs-lookup"><span data-stu-id="2911e-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="2911e-212">Кроме того может быть заманчивой слишком сложно любое исключение в желания для функции «простой», которая возвращает тип «лучше»:</span><span class="sxs-lookup"><span data-stu-id="2911e-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="2911e-213">К сожалению `tryReadAllText` могут создавать многочисленные исключения с учетом множество вещей, которые могут произойти в файловой системе, и этот код немедленно удаляет любые сведения о том, что может фактически пошло не так в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2911e-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="2911e-214">Если необходимо заменить этот код с типом результатов, вы будете обратно в «stringly типизированные» ошибка при синтаксическом анализе сообщения:</span><span class="sxs-lookup"><span data-stu-id="2911e-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="2911e-215">А сам объект исключения в `Error` конструктор просто вызывает должным образом работать с тип исключения во время вызова, а не в функции.</span><span class="sxs-lookup"><span data-stu-id="2911e-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="2911e-216">Это фактически создает checked исключений, которые заведомо unfun обрабатывать как вызывающий объект API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2911e-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="2911e-217">— Это хорошая альтернатива для приведенных выше примерах для перехвата *конкретных* исключения и возвращаемое значение может применяться в контексте этого исключения.</span><span class="sxs-lookup"><span data-stu-id="2911e-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="2911e-218">При изменении `tryReadAllText` следующим образом, функция `None` имеет дополнительные значения:</span><span class="sxs-lookup"><span data-stu-id="2911e-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="2911e-219">Вместо функции универсальным, эта функция теперь правильную обработку случае если файл не найден и назначьте этого значения возврата.</span><span class="sxs-lookup"><span data-stu-id="2911e-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="2911e-220">Это возвращаемое значение можно сопоставить в этом случае ошибка, не отменяя все контекстные сведения или принудительное вызывающим объектам работать со случаем, который может быть не актуальной на данный момент в коде.</span><span class="sxs-lookup"><span data-stu-id="2911e-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="2911e-221">Типы, такие как `Result<'Success, 'Error>` подходят для основных операций, где они не являются вложенными и дополнительные типы F # удобны для представления, когда что-то может либо возвращают *что-нибудь* или *ничего*.</span><span class="sxs-lookup"><span data-stu-id="2911e-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="2911e-222">Они не замены для исключений, хотя и не должны использоваться с целью для замены исключения.</span><span class="sxs-lookup"><span data-stu-id="2911e-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="2911e-223">Вместо этого они должны применяться осмотрительно для определенных аспектов адрес исключения и ошибки политики управления целевых способами.</span><span class="sxs-lookup"><span data-stu-id="2911e-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="2911e-224">Частичное применение и освободить точки программирование</span><span class="sxs-lookup"><span data-stu-id="2911e-224">Partial application and point-free programming</span></span>

<span data-ttu-id="2911e-225">F # поддерживает частичное применение и, следовательно, различные способы программы в стиле освободить точки.</span><span class="sxs-lookup"><span data-stu-id="2911e-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="2911e-226">Это может быть использовано для повторного использования кода в модуль или что-то реализации, но обычно это не что-нибудь для предоставления публично.</span><span class="sxs-lookup"><span data-stu-id="2911e-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="2911e-227">В общем случае точки освободить программирования не является тем, сама по себе и можно добавить когнитивных перешагнуть барьер для тех, кто не занимается стиль.</span><span class="sxs-lookup"><span data-stu-id="2911e-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="2911e-228">Не используйте частичное применение и каррирования в открытых интерфейсах API</span><span class="sxs-lookup"><span data-stu-id="2911e-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="2911e-229">За исключением мало использование частичное применение в открытых интерфейсах API могут показаться сложными для потребителей.</span><span class="sxs-lookup"><span data-stu-id="2911e-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="2911e-230">Как правило `let`-связанных значений в коде F #, **значения**, а не **значений функций**.</span><span class="sxs-lookup"><span data-stu-id="2911e-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="2911e-231">Смешивание вместе значений и значений функций может привести к сохранение небольшое количество строк кода за счет бит когнитивных издержек, особенно в том случае, если вместе с операторами, такие как `>>` для создания функции.</span><span class="sxs-lookup"><span data-stu-id="2911e-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="2911e-232">Следует учитывать влияние инструментарий для освобождения точки программирования</span><span class="sxs-lookup"><span data-stu-id="2911e-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="2911e-233">Каррированные функции метки не для их аргументов.</span><span class="sxs-lookup"><span data-stu-id="2911e-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="2911e-234">Это имеет последствия для работы с проектами.</span><span class="sxs-lookup"><span data-stu-id="2911e-234">This has tooling implications.</span></span> <span data-ttu-id="2911e-235">Рассмотрим следующие две функции:</span><span class="sxs-lookup"><span data-stu-id="2911e-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="2911e-236">Оба являются допустимым функции, но `funcWithApplication` является каррированные функции.</span><span class="sxs-lookup"><span data-stu-id="2911e-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="2911e-237">При наведении указателя мыши на их типы в редакторе можно увидеть:</span><span class="sxs-lookup"><span data-stu-id="2911e-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="2911e-238">В источнике вызова с указанием подсказки в инструментарий, такой как Visual Studio не даст значимую информацию о том, что `string` и `int` фактически представляют типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="2911e-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="2911e-239">При возникновении освободить точки кода, подобного `funcWithApplication` , является общедоступной, рекомендуется сделать полную η-расширения, чтобы средства можно обратить ваше внимание на значимые имена для аргументов.</span><span class="sxs-lookup"><span data-stu-id="2911e-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="2911e-240">Кроме того отладка освободить точки кода может оказаться сложной задачей, если вообще.</span><span class="sxs-lookup"><span data-stu-id="2911e-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="2911e-241">Средства отладки зависит от значений, привязанный к именам (например, `let` привязок), чтобы можно было проверить середине промежуточных значений выполнения.</span><span class="sxs-lookup"><span data-stu-id="2911e-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="2911e-242">Если код не имеет значений для проверки, нет ничего для отладки.</span><span class="sxs-lookup"><span data-stu-id="2911e-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="2911e-243">В будущем, средства отладки может развиваться синтезировать эти значения в зависимости от ранее выполненного пути, но не рекомендуется hedge вашей подходящих на *потенциальных* функциональные возможности отладки.</span><span class="sxs-lookup"><span data-stu-id="2911e-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="2911e-244">Рассмотрим частичное применение как способ для уменьшения внутреннего стандартного</span><span class="sxs-lookup"><span data-stu-id="2911e-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="2911e-245">В отличие от предыдущей точке частичное применение — это здорово средство для снижения стандартного внутри приложения или более глубокого внутренних API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2911e-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="2911e-246">Может быть полезным для модульного тестирования реализации более сложной API, в которых стандартного является неудобной для работы с.</span><span class="sxs-lookup"><span data-stu-id="2911e-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="2911e-247">Например в следующем коде показано, как это можно сделать какие инфраструктур наиболее макетирования позволяют без учета внешней зависимости такую платформу и изучая связана bespoke API.</span><span class="sxs-lookup"><span data-stu-id="2911e-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="2911e-248">Например рассмотрим следующие решения топографии:</span><span class="sxs-lookup"><span data-stu-id="2911e-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="2911e-249">`ImplementationLogic.fsproj` Например, может предоставлять код:</span><span class="sxs-lookup"><span data-stu-id="2911e-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="2911e-250">Модульное тестирование `Transactions.doTransaction` в `ImplementationLogic.Tests.fspoj` прост:</span><span class="sxs-lookup"><span data-stu-id="2911e-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="2911e-251">Частично применение `doTransaction` имитации контекстом объекта можно вызывать функции во всех модульных тестов без необходимости создания макеты контекста каждый раз:</span><span class="sxs-lookup"><span data-stu-id="2911e-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="2911e-252">Этот способ не следует применять ко всем компонентам на всей базе кода, но это хороший способ уменьшить стандартный для сложных внутренних компонентов и модульного тестирования эти внутренние компоненты.</span><span class="sxs-lookup"><span data-stu-id="2911e-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="2911e-253">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="2911e-253">Access control</span></span>

<span data-ttu-id="2911e-254">F # имеет несколько возможностей для [управления доступом к](../language-reference/access-control.md), унаследованное от того, что доступно в среде выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="2911e-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="2911e-255">Это не просто можно использовать для типов — их можно использовать для функций, слишком.</span><span class="sxs-lookup"><span data-stu-id="2911e-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="2911e-256">Предпочтение не`public` типов и членов, пока вы они нужны в виде общедоступной.</span><span class="sxs-lookup"><span data-stu-id="2911e-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="2911e-257">Это сводит к минимуму какие несколько потребителей для</span><span class="sxs-lookup"><span data-stu-id="2911e-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="2911e-258">Стремятся сохранить все функциональные возможности поддержки `private`.</span><span class="sxs-lookup"><span data-stu-id="2911e-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="2911e-259">Рассмотрите возможность использования `[<AutoOpen>]` на закрытого модуля вспомогательных функций, если они станут многочисленные.</span><span class="sxs-lookup"><span data-stu-id="2911e-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="2911e-260">Определение типа и универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="2911e-260">Type inference and generics</span></span>

<span data-ttu-id="2911e-261">Вывод типа, которые можно сохранить большой объем стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="2911e-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="2911e-262">И Автоматическое обобщение в компиляторе F # может помочь написать более общий код с практически никаких дополнительных действий со стороны пользователя.</span><span class="sxs-lookup"><span data-stu-id="2911e-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="2911e-263">Однако эти компоненты не всегда хорошо.</span><span class="sxs-lookup"><span data-stu-id="2911e-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="2911e-264">Рассмотрим маркировкой явные типы в открытых интерфейсах API: имена аргументов и не следует полагаться на определение типа для этого.</span><span class="sxs-lookup"><span data-stu-id="2911e-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="2911e-265">Это обусловлено тем, **вы** должно быть в элементе управления фигуры API, не компилятора.</span><span class="sxs-lookup"><span data-stu-id="2911e-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="2911e-266">Несмотря на то, что компилятор может сделать нормально задание на вывод типов автоматически, существует возможность иметь форму изменения в API, если внутренние компоненты, которые он основывается на были изменены типы.</span><span class="sxs-lookup"><span data-stu-id="2911e-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="2911e-267">Это может быть неподходящей, но это почти наверняка приведет к критическим изменением API, потребителей потока данных будет иметь дело с.</span><span class="sxs-lookup"><span data-stu-id="2911e-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="2911e-268">Вместо этого если явным образом управления фигуры открытые API, можно управлять эти критические изменения.</span><span class="sxs-lookup"><span data-stu-id="2911e-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="2911e-269">В терминах ддд это может рассматриваться как уровень защиты от повреждения.</span><span class="sxs-lookup"><span data-stu-id="2911e-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="2911e-270">Следует давать понятное имя для универсальных аргументов.</span><span class="sxs-lookup"><span data-stu-id="2911e-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="2911e-271">Если вы пишете действительно универсального кода, который не относится к определенному домену, понятное имя может помочь другим программистам основные сведения о домене, при работе в.</span><span class="sxs-lookup"><span data-stu-id="2911e-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="2911e-272">Например, параметр типа с именем `'Document` в контексте взаимодействия с документом базы данных упрощает яснее, типы универсального документа может быть принят функции или элемента, вы работаете с.</span><span class="sxs-lookup"><span data-stu-id="2911e-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="2911e-273">Рекомендуется называть PascalCase в параметрах универсального типа.</span><span class="sxs-lookup"><span data-stu-id="2911e-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="2911e-274">Это общий способ для выполнения различных операций в .NET, поэтому рекомендуется использовать PascalCase вместо snake_case или camelCase.</span><span class="sxs-lookup"><span data-stu-id="2911e-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="2911e-275">Наконец Автоматическое обобщение не всегда является весьма полезным для пользователей, незнакомых с F # или большой базе кода.</span><span class="sxs-lookup"><span data-stu-id="2911e-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="2911e-276">Требуется когнитивных с помощью компонентов, которые являются универсальными.</span><span class="sxs-lookup"><span data-stu-id="2911e-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="2911e-277">Кроме того Если автоматически обобщенной функции не используются для различных типов входных данных (только в том случае, если они предназначены для использования таким образом не говоря), то не имеет смысла реальные им быть универсальным на момент времени.</span><span class="sxs-lookup"><span data-stu-id="2911e-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="2911e-278">Всегда учитывается, если код, который вы пишете фактически выиграет от быть универсальным.</span><span class="sxs-lookup"><span data-stu-id="2911e-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="2911e-279">Производительность</span><span class="sxs-lookup"><span data-stu-id="2911e-279">Performance</span></span>

<span data-ttu-id="2911e-280">F # значения являются неизменяемыми, по умолчанию, что позволяет избежать определенные классы ошибок (особенно эти связанные с параллелизмом и параллелизма).</span><span class="sxs-lookup"><span data-stu-id="2911e-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="2911e-281">Однако в некоторых случаях для достижения оптимальной (или даже приемлемого) эффективность времени выполнения или выделения памяти диапазон работы может лучше всего реализовать с помощью изменение состояния на месте.</span><span class="sxs-lookup"><span data-stu-id="2911e-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="2911e-282">Это можно сделать в согласие на основе, то есть с помощью F # с `mutable` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2911e-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="2911e-283">Однако использование `mutable` в языке F # могут счесть соответствует функциональной чистоты.</span><span class="sxs-lookup"><span data-stu-id="2911e-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="2911e-284">Это нормально, если настроить ожиданиям из чистоты для [ссылочной прозрачности](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="2911e-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="2911e-285">Ссылочная прозрачность - не чистоты - — конечная цель при написании функции F #.</span><span class="sxs-lookup"><span data-stu-id="2911e-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="2911e-286">Это позволяет писать функциональной интерфейс через реализацию на основе изменений для критического кода производительности.</span><span class="sxs-lookup"><span data-stu-id="2911e-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="2911e-287">Поместите код, изменяемые в неизменяемый интерфейсов</span><span class="sxs-lookup"><span data-stu-id="2911e-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="2911e-288">С ссылочной прозрачности как целевой крайне важно написать код, который не предоставляет изменяемый underbelly функций, критический с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="2911e-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="2911e-289">Например, следующий код реализует `Array.contains` функции в основной библиотеке F #:</span><span class="sxs-lookup"><span data-stu-id="2911e-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="2911e-290">Несколько раз при вызове этой функции не изменяет базовый массив и не требуется поддерживать любое изменяемое состояние, в его использования.</span><span class="sxs-lookup"><span data-stu-id="2911e-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="2911e-291">Он прозрачно со ссылочным, несмотря на то, что изменение использует практически в каждой строке кода внутри него.</span><span class="sxs-lookup"><span data-stu-id="2911e-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="2911e-292">Рассмотрим, инкапсулируя изменяемых данных в классах</span><span class="sxs-lookup"><span data-stu-id="2911e-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="2911e-293">Предыдущий пример использовать одной функции для инкапсуляции операций с использованием изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="2911e-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="2911e-294">Это не всегда достаточно для более сложных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="2911e-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="2911e-295">Рассмотрим следующий набор функций:</span><span class="sxs-lookup"><span data-stu-id="2911e-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="2911e-296">Данный пример кода является высокопроизводительных, но предоставляет структуру данных на основе изменений, что вызывающие объекты отвечают за обеспечение.</span><span class="sxs-lookup"><span data-stu-id="2911e-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="2911e-297">Это может быть перенесено внутри класса без базовых членов, которые можно изменить:</span><span class="sxs-lookup"><span data-stu-id="2911e-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="2911e-298">`Closure1Table` Инкапсулирует базовой структуры данных на основе изменений, тем самым не выполняется принудительно вызывающих объектов для сохранения структуры данных.</span><span class="sxs-lookup"><span data-stu-id="2911e-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="2911e-299">Классы являются мощным средством для инкапсуляции данных и подпрограммы, которые основаны на изменение без предоставления сведений вызывающим объектам.</span><span class="sxs-lookup"><span data-stu-id="2911e-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="2911e-300">Предпочтение `let mutable` для ссылочные ячейки</span><span class="sxs-lookup"><span data-stu-id="2911e-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="2911e-301">Ссылочные ячейки являются способ представления ссылку на значение, а не само значение.</span><span class="sxs-lookup"><span data-stu-id="2911e-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="2911e-302">Несмотря на то, что они могут использоваться для важных для производительности кода, они обычно не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="2911e-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="2911e-303">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="2911e-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="2911e-304">Использовать ссылочную ячейку теперь «засоряет» все последующие кода с входящим разыменования и повторно ссылки на базовые данные.</span><span class="sxs-lookup"><span data-stu-id="2911e-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="2911e-305">Вместо этого рассмотрите возможность `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="2911e-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="2911e-306">Помимо единой точки изменений в середине лямбда-выражения, все остальные кода, касается `acc` можно сделать, таким образом, чтобы не отличается с использованием обычной `let`-привязан постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="2911e-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="2911e-307">Это поможет упростить его изменение во времени.</span><span class="sxs-lookup"><span data-stu-id="2911e-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="2911e-308">Программирование объектов</span><span class="sxs-lookup"><span data-stu-id="2911e-308">Object programming</span></span>

<span data-ttu-id="2911e-309">F # имеет полную поддержку для объектов и объектно ориентированные концепции (ОО).</span><span class="sxs-lookup"><span data-stu-id="2911e-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="2911e-310">Хотя многие понятия OO мощным и удобным, не все из них идеально подходят для использования.</span><span class="sxs-lookup"><span data-stu-id="2911e-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="2911e-311">Перечисленные ниже представлено руководство по категориям OO функций высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="2911e-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="2911e-312">**Рассмотрите возможность использования этих функций во многих ситуациях:**</span><span class="sxs-lookup"><span data-stu-id="2911e-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="2911e-313">Нотация с точками (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="2911e-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="2911e-314">Члены экземпляров</span><span class="sxs-lookup"><span data-stu-id="2911e-314">Instance members</span></span>
* <span data-ttu-id="2911e-315">Неявные конструкторы</span><span class="sxs-lookup"><span data-stu-id="2911e-315">Implicit constructors</span></span>
* <span data-ttu-id="2911e-316">Статические члены</span><span class="sxs-lookup"><span data-stu-id="2911e-316">Static members</span></span>
* <span data-ttu-id="2911e-317">Обозначения индексатора (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="2911e-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="2911e-318">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="2911e-318">Named and Optional arguments</span></span>
* <span data-ttu-id="2911e-319">Интерфейсы и реализации интерфейса</span><span class="sxs-lookup"><span data-stu-id="2911e-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="2911e-320">**Не достигнет первым для этих возможностей, но осмотрительно их применяют, когда они удобны для решения проблемы:**</span><span class="sxs-lookup"><span data-stu-id="2911e-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="2911e-321">Перегрузка методов</span><span class="sxs-lookup"><span data-stu-id="2911e-321">Method overloading</span></span>
* <span data-ttu-id="2911e-322">Инкапсулированный изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="2911e-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="2911e-323">Операторы типов</span><span class="sxs-lookup"><span data-stu-id="2911e-323">Operators on types</span></span>
* <span data-ttu-id="2911e-324">Свойства Auto</span><span class="sxs-lookup"><span data-stu-id="2911e-324">Auto properties</span></span>
* <span data-ttu-id="2911e-325">Реализация `IDisposable` и `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="2911e-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="2911e-326">Расширения типов</span><span class="sxs-lookup"><span data-stu-id="2911e-326">Type extensions</span></span>
* <span data-ttu-id="2911e-327">События</span><span class="sxs-lookup"><span data-stu-id="2911e-327">Events</span></span>
* <span data-ttu-id="2911e-328">Структуры</span><span class="sxs-lookup"><span data-stu-id="2911e-328">Structs</span></span>
* <span data-ttu-id="2911e-329">Делегаты</span><span class="sxs-lookup"><span data-stu-id="2911e-329">Delegates</span></span>
* <span data-ttu-id="2911e-330">перечислениям;</span><span class="sxs-lookup"><span data-stu-id="2911e-330">Enums</span></span>

<span data-ttu-id="2911e-331">**Если требуется использовать их Избегайте эти функции:**</span><span class="sxs-lookup"><span data-stu-id="2911e-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="2911e-332">Иерархии типа на основе наследования и наследование реализации</span><span class="sxs-lookup"><span data-stu-id="2911e-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="2911e-333">Значения NULL и `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="2911e-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="2911e-334">Предпочтение компоновки наследования</span><span class="sxs-lookup"><span data-stu-id="2911e-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="2911e-335">[Композиция через наследование](https://en.wikipedia.org/wiki/Composition_over_inheritance) широко устойчивую, может следовать хороший код F #.</span><span class="sxs-lookup"><span data-stu-id="2911e-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="2911e-336">Основной задачей является следует предоставить базовый класс и не принудительно наследовать от этого базового класса, чтобы функции от вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="2911e-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="2911e-337">Выражения объекта используются для реализации интерфейсов, если вам не нужен класс</span><span class="sxs-lookup"><span data-stu-id="2911e-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="2911e-338">[Выражения объектов](../language-reference/object-expressions.md) позволяют реализовать интерфейсы на ходу, привязывая реализованный интерфейс к значению без необходимости делать это в теле класса.</span><span class="sxs-lookup"><span data-stu-id="2911e-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="2911e-339">Это удобно, особенно в том случае, если вы _только_ необходимо реализовать интерфейс и не требуются для полного класса.</span><span class="sxs-lookup"><span data-stu-id="2911e-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="2911e-340">Например, ниже приведен код, выполняемый в [Ionide](http://ionide.io/) для обеспечения действие исправления кода, если вы добавили символ, не нужно `open` инструкции для:</span><span class="sxs-lookup"><span data-stu-id="2911e-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="2911e-341">Поскольку нет необходимости для класса при взаимодействии с API кода Visual Studio, выражения объекта являются идеальным средством для этого.</span><span class="sxs-lookup"><span data-stu-id="2911e-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="2911e-342">Их также можно использовать для модульного тестирования, чтобы заглушки для интерфейса с помощью процедуры тестирования в нерегламентированной форме.</span><span class="sxs-lookup"><span data-stu-id="2911e-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="2911e-343">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="2911e-343">Type Abbreviations</span></span>

<span data-ttu-id="2911e-344">[Аббревиатуры типов](../language-reference/type-abbreviations.md) — это удобный способ назначить метку другого типа, например сигнатуру функции или более сложного типа.</span><span class="sxs-lookup"><span data-stu-id="2911e-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="2911e-345">Например, следующий псевдоним присваивается метка что требуется для определения вычислений с [CNTK](https://www.microsoft.com/cognitive-toolkit/), глубокая обучения библиотеки:</span><span class="sxs-lookup"><span data-stu-id="2911e-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="2911e-346">`Computation` Имя является удобным способом для обозначения любая функция, которая совпадает с подписью, это задание псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="2911e-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="2911e-347">С помощью сокращенные обозначения типов следующим образом является удобным и позволяет более лаконичный код.</span><span class="sxs-lookup"><span data-stu-id="2911e-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="2911e-348">Старайтесь не использовать для представления домена сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="2911e-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="2911e-349">Несмотря на то, что сокращенные обозначения типов удобны для присвоения имени сигнатур функций, они могут ввести в заблуждение при сокращение параметра других типов.</span><span class="sxs-lookup"><span data-stu-id="2911e-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="2911e-350">Рассмотрим это сокращенная форма:</span><span class="sxs-lookup"><span data-stu-id="2911e-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="2911e-351">Это может вызывать путаницу несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="2911e-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="2911e-352">`BufferSize` не является абстракцией; Это просто другое название для целого числа.</span><span class="sxs-lookup"><span data-stu-id="2911e-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="2911e-353">Если `BufferSize` предоставляется в открытый интерфейс API, его можно легко пониматься больше, чем просто означает `int`.</span><span class="sxs-lookup"><span data-stu-id="2911e-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="2911e-354">Как правило, имеет несколько атрибутов, к ним типов домена и не являются простыми типами, например `int`.</span><span class="sxs-lookup"><span data-stu-id="2911e-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="2911e-355">Это сокращение нарушает этого предположения.</span><span class="sxs-lookup"><span data-stu-id="2911e-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="2911e-356">Регистр `BufferSize` (PascalCase) означает, что этот тип содержит дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="2911e-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="2911e-357">Этот псевдоним не обеспечивает четкое по сравнению с предоставлением именованный аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="2911e-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="2911e-358">Сокращение не будут проявляться в скомпилированных IL; он представляет собой целое, и этот псевдоним — это конструкция, во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="2911e-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="2911e-359">Таким образом, ловушек с сокращенные обозначения типов для этого используется **не** абстракции по типам, они сокращение параметра.</span><span class="sxs-lookup"><span data-stu-id="2911e-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="2911e-360">В предыдущем примере `BufferSize` только `int` на самом деле с без дополнительных данных, а также все преимущества из системы типов, что помимо `int` уже есть.</span><span class="sxs-lookup"><span data-stu-id="2911e-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
