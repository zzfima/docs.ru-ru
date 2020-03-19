---
title: Соглашения о написании кода на F#
description: Изучите общие руководящие принципы и идиомы при написании кода F.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401151"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="a7137-103">Соглашения о написании кода на F#</span><span class="sxs-lookup"><span data-stu-id="a7137-103">F# coding conventions</span></span>

<span data-ttu-id="a7137-104">Следующие конвенции сформулированы на основе опыта работы с большими базами кодов F.</span><span class="sxs-lookup"><span data-stu-id="a7137-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="a7137-105">[Пять принципов хорошего кода ФЗ](index.md#five-principles-of-good-f-code) являются основой каждой рекомендации.</span><span class="sxs-lookup"><span data-stu-id="a7137-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="a7137-106">Они связаны с [руководящими принципами проектирования компонентов F,,](component-design-guidelines.md)но применимы для любого кода F, а не только компонентов, таких как библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a7137-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="a7137-107">Организационный код</span><span class="sxs-lookup"><span data-stu-id="a7137-107">Organizing code</span></span>

<span data-ttu-id="a7137-108">Фз имеет два основных способа организации кода: модули и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7137-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="a7137-109">Они похожи, но имеют следующие различия:</span><span class="sxs-lookup"><span data-stu-id="a7137-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="a7137-110">Пространства имен компилируются как пространства имен .NET.</span><span class="sxs-lookup"><span data-stu-id="a7137-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="a7137-111">Модули компилируются как статические классы.</span><span class="sxs-lookup"><span data-stu-id="a7137-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="a7137-112">Именные пространства всегда находятся на высшем уровне.</span><span class="sxs-lookup"><span data-stu-id="a7137-112">Namespaces are always top level.</span></span> <span data-ttu-id="a7137-113">Модули могут быть на высшем уровне и вложены в другие модули.</span><span class="sxs-lookup"><span data-stu-id="a7137-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="a7137-114">Пространства имен могут охватывать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="a7137-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="a7137-115">Модули не могут.</span><span class="sxs-lookup"><span data-stu-id="a7137-115">Modules cannot.</span></span>
* <span data-ttu-id="a7137-116">Модули могут `[<RequireQualifiedAccess>]` быть `[<AutoOpen>]`украшены и .</span><span class="sxs-lookup"><span data-stu-id="a7137-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="a7137-117">Следующие рекомендации помогут вам использовать их для организации кода.</span><span class="sxs-lookup"><span data-stu-id="a7137-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="a7137-118">Предпочитаюте пространства имен на верхнем уровне</span><span class="sxs-lookup"><span data-stu-id="a7137-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="a7137-119">Для любого публично расходного кода пространства имен являются предпочтительными для модулей на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="a7137-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="a7137-120">Поскольку они компилируются как области имен .NET, они расходуются из C-класса без проблем.</span><span class="sxs-lookup"><span data-stu-id="a7137-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="a7137-121">Использование модуля верхнего уровня может отличаться от вызова только от F, но для потребителей C, абоненты могут быть удивлены, имея право на доступ `MyClass` к `MyCode` модулю.</span><span class="sxs-lookup"><span data-stu-id="a7137-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="a7137-122">Тщательно нанесите`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="a7137-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="a7137-123">Конструкция `[<AutoOpen>]` может загрязнять область того, что доступно для абонентов, и ответ на то, где что-то происходит от является "волшебство".</span><span class="sxs-lookup"><span data-stu-id="a7137-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="a7137-124">Это не очень хорошо.</span><span class="sxs-lookup"><span data-stu-id="a7137-124">This is not a good thing.</span></span> <span data-ttu-id="a7137-125">Исключением из этого правила является сама базовая библиотека F » (хотя этот факт также немного противоречив).</span><span class="sxs-lookup"><span data-stu-id="a7137-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="a7137-126">Тем не менее, это удобство, если у вас есть функция помощника для общедоступного API, который вы хотите организовать отдельно от этого общедоступного API.</span><span class="sxs-lookup"><span data-stu-id="a7137-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="a7137-127">Это позволяет чисто отделить детали реализации от общедоступного API функции без необходимости полностью квалифицировать помощника каждый раз, когда вы называете его.</span><span class="sxs-lookup"><span data-stu-id="a7137-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="a7137-128">Кроме того, разоблачение методов расширения и раздатчиков выражения `[<AutoOpen>]`на уровне пространства имен может быть аккуратно выражено с .</span><span class="sxs-lookup"><span data-stu-id="a7137-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="a7137-129">Используйте `[<RequireQualifiedAccess>]` всякий раз, когда имена могут конфликтовать или вы чувствуете, что это помогает с читаемостью</span><span class="sxs-lookup"><span data-stu-id="a7137-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="a7137-130">Добавление `[<RequireQualifiedAccess>]` атрибута к модулю указывает на то, что модуль не может быть открыт и что ссылки на элементы модуля требуют явного квалифицированного доступа.</span><span class="sxs-lookup"><span data-stu-id="a7137-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="a7137-131">Например, `Microsoft.FSharp.Collections.List` модуль имеет этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="a7137-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="a7137-132">Это полезно, когда функции и значения в модуле имеют имена, которые могут впротиворечить именам в других модулях.</span><span class="sxs-lookup"><span data-stu-id="a7137-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="a7137-133">Требование квалифицированного доступа может значительно повысить долгосрочную удобство обслуживания и эволюционность библиотеки.</span><span class="sxs-lookup"><span data-stu-id="a7137-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="a7137-134">Сортировка `open` заявлений топологически</span><span class="sxs-lookup"><span data-stu-id="a7137-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="a7137-135">В ФЗ важен порядок деклараций, `open` в том числе с заявлениями.</span><span class="sxs-lookup"><span data-stu-id="a7137-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="a7137-136">Это не похоже на c', где эффект `using` и `using static` не зависит от заказа этих инструкций в файле.</span><span class="sxs-lookup"><span data-stu-id="a7137-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="a7137-137">В F- элементы, открытые в область, могут затмевать других уже присутствующих.</span><span class="sxs-lookup"><span data-stu-id="a7137-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="a7137-138">Это означает, что `open` переупорядочение инструкций может изменить значение кода.</span><span class="sxs-lookup"><span data-stu-id="a7137-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="a7137-139">В результате не рекомендуется проводить `open` произвольные сортировки всех инструкций (например, альфанумерически), чтобы не создавать другое поведение, которое можно было бы ожидать.</span><span class="sxs-lookup"><span data-stu-id="a7137-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="a7137-140">Вместо этого, мы рекомендуем вам сортировать их [топологически](https://en.wikipedia.org/wiki/Topological_sorting); то есть, `open` заказать ваши заявления в порядке, в котором _слои_ вашей системы определены.</span><span class="sxs-lookup"><span data-stu-id="a7137-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="a7137-141">Также может быть рассмотренвопрос о проведении алфавитной сортировки в различных топологических слоях.</span><span class="sxs-lookup"><span data-stu-id="a7137-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="a7137-142">В качестве примера можно сделать топологический сортировку для общедоступного файла API-сервиса компиляционов F's:</span><span class="sxs-lookup"><span data-stu-id="a7137-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="a7137-143">Обратите внимание, что разрыв линии разделяет топологические слои, при этом каждый слой затем сортируется альфанумерически.</span><span class="sxs-lookup"><span data-stu-id="a7137-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="a7137-144">Это чисто организует код без случайного затенения значений.</span><span class="sxs-lookup"><span data-stu-id="a7137-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="a7137-145">Используйте классы для содержания значений, которые имеют побочные эффекты</span><span class="sxs-lookup"><span data-stu-id="a7137-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="a7137-146">Есть много случаев, когда инициализация значения может иметь побочные эффекты, такие как мгновенное воспроизведение контекста в базу данных или другой удаленный ресурс.</span><span class="sxs-lookup"><span data-stu-id="a7137-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="a7137-147">Заманчиво инициализировать такие вещи в модуле и использовать его в последующих функциях:</span><span class="sxs-lookup"><span data-stu-id="a7137-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="a7137-148">Это часто плохая идея по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="a7137-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="a7137-149">Во-первых, конфигурация приложения заталкивается в кодовую базу с `dep1` и `dep2`.</span><span class="sxs-lookup"><span data-stu-id="a7137-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="a7137-150">Это трудно поддерживать в больших баз кода.</span><span class="sxs-lookup"><span data-stu-id="a7137-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="a7137-151">Во-вторых, статические инициализированные данные не должны включать значения, которые не являются безопасными для потока, если компонент сам будет использовать несколько потоков.</span><span class="sxs-lookup"><span data-stu-id="a7137-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="a7137-152">Это явно нарушается `dep3`.</span><span class="sxs-lookup"><span data-stu-id="a7137-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="a7137-153">Наконец, инициализация модуля компилируется в статический конструктор для всего блока компиляции.</span><span class="sxs-lookup"><span data-stu-id="a7137-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="a7137-154">Если какая-либо ошибка возникает в инициализации значения, связанного с пуском в этом модуле, она проявляется как `TypeInitializationException` ошибка, которая затем кэшируется на протяжении всего срока службы приложения.</span><span class="sxs-lookup"><span data-stu-id="a7137-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="a7137-155">Это может быть трудно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="a7137-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="a7137-156">Существует, как правило, внутреннее исключение, что вы можете попытаться рассуждать о, но если нет, то никто не знает, что первопричина.</span><span class="sxs-lookup"><span data-stu-id="a7137-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="a7137-157">Вместо этого просто используйте простой класс для хранения зависимостей:</span><span class="sxs-lookup"><span data-stu-id="a7137-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="a7137-158">Это позволяет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a7137-158">This enables the following:</span></span>

1. <span data-ttu-id="a7137-159">Нажатие любого зависимого состояния за пределы самого API.</span><span class="sxs-lookup"><span data-stu-id="a7137-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="a7137-160">Конфигурация теперь может быть выполнена за пределами API.</span><span class="sxs-lookup"><span data-stu-id="a7137-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="a7137-161">Ошибки в инициализации для зависимых значений вряд ли проявляются как `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="a7137-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="a7137-162">Теперь API легче тестировать.</span><span class="sxs-lookup"><span data-stu-id="a7137-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="a7137-163">Управление ошибками</span><span class="sxs-lookup"><span data-stu-id="a7137-163">Error management</span></span>

<span data-ttu-id="a7137-164">Управление ошибками в больших системах является сложной и тонкой работы, и Есть нет серебряных пуль в обеспечении ваших систем являются отказоустойчивыми и ведут себя хорошо.</span><span class="sxs-lookup"><span data-stu-id="a7137-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="a7137-165">Следующие руководящие принципы должны дать рекомендации в области навигации по этому сложному пространству.</span><span class="sxs-lookup"><span data-stu-id="a7137-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="a7137-166">Представлять случаи ошибок и незаконное состояние в типах, присущих вашему домену</span><span class="sxs-lookup"><span data-stu-id="a7137-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="a7137-167">С [дискриминируемыми союзами,](../language-reference/discriminated-unions.md)ФЗ дает вам возможность представлять неисправное состояние программы в вашей системе типа.</span><span class="sxs-lookup"><span data-stu-id="a7137-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="a7137-168">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7137-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="a7137-169">В этом случае существует три известных способа, что снятие денег с банковского счета может потерпеть неудачу.</span><span class="sxs-lookup"><span data-stu-id="a7137-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="a7137-170">Каждый случай ошибки представлен в типе, и таким образом может быть рассмотрен безопасно на протяжении всей программы.</span><span class="sxs-lookup"><span data-stu-id="a7137-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="a7137-171">В общем случае, если вы можете моделировать различные способы, что что-то может **потерпеть неудачу** в вашем домене, то код обработки ошибок больше не рассматривается как то, что вы должны иметь дело с в дополнение к регулярному потоку программы.</span><span class="sxs-lookup"><span data-stu-id="a7137-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="a7137-172">Это просто часть нормального потока программы, и не считается **исключительным**.</span><span class="sxs-lookup"><span data-stu-id="a7137-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="a7137-173">Есть два основных преимущества этого:</span><span class="sxs-lookup"><span data-stu-id="a7137-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="a7137-174">Это проще поддерживать, как ваш домен меняется с течением времени.</span><span class="sxs-lookup"><span data-stu-id="a7137-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="a7137-175">Случаи ошибок проще удельного тестирования.</span><span class="sxs-lookup"><span data-stu-id="a7137-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="a7137-176">Используйте исключения, если ошибки не могут быть представлены с типами</span><span class="sxs-lookup"><span data-stu-id="a7137-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="a7137-177">Не все ошибки могут быть представлены в проблемной области.</span><span class="sxs-lookup"><span data-stu-id="a7137-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="a7137-178">Эти виды неисправностей являются *исключительными* по своему характеру, следовательно, способность поднимать и ловить исключения в F.</span><span class="sxs-lookup"><span data-stu-id="a7137-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="a7137-179">Во-первых, рекомендуется прочитать [Руководящие принципы проектирования исключений.](../../standard/design-guidelines/exceptions.md)</span><span class="sxs-lookup"><span data-stu-id="a7137-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="a7137-180">Они также применимы к ФЗ.</span><span class="sxs-lookup"><span data-stu-id="a7137-180">These are also applicable to F#.</span></span>

<span data-ttu-id="a7137-181">Основные конструкции, доступные в ФЗ для целей повышения исключений, должны рассматриваться в следующем порядке предпочтений:</span><span class="sxs-lookup"><span data-stu-id="a7137-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="a7137-182">Компонент</span><span class="sxs-lookup"><span data-stu-id="a7137-182">Function</span></span> | <span data-ttu-id="a7137-183">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7137-183">Syntax</span></span> | <span data-ttu-id="a7137-184">Назначение</span><span class="sxs-lookup"><span data-stu-id="a7137-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="a7137-185">Поднимает `System.ArgumentNullException` с указанным названием аргумента.</span><span class="sxs-lookup"><span data-stu-id="a7137-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="a7137-186">Поднимает `System.ArgumentException` с указанным названием аргумента и сообщением.</span><span class="sxs-lookup"><span data-stu-id="a7137-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="a7137-187">Поднимает `System.InvalidOperationException` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="a7137-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="a7137-188">Механизм общего назначения для метания исключений.</span><span class="sxs-lookup"><span data-stu-id="a7137-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="a7137-189">Поднимает `System.Exception` с указанным сообщением.</span><span class="sxs-lookup"><span data-stu-id="a7137-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="a7137-190">Поднимает `System.Exception` сообщение, определяемые строкой формата и ее входными данными.</span><span class="sxs-lookup"><span data-stu-id="a7137-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="a7137-191">`nullArg`Используйте, `invalidOp` `invalidArg` и в качестве `ArgumentException` `InvalidOperationException` механизма бросать, `ArgumentNullException`и когда это уместно.</span><span class="sxs-lookup"><span data-stu-id="a7137-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="a7137-192">`failwith` Функции `failwithf` и функции, как правило, следует избегать, поскольку они повышают базовый `Exception` тип, а не конкретное исключение.</span><span class="sxs-lookup"><span data-stu-id="a7137-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="a7137-193">В рамках [Руководящих принципов проектирования исключений](../../standard/design-guidelines/exceptions.md)необходимо, когда это возможно, вы можете создать более конкретные исключения.</span><span class="sxs-lookup"><span data-stu-id="a7137-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="a7137-194">Использование синтаксиса обработки исключений</span><span class="sxs-lookup"><span data-stu-id="a7137-194">Using exception-handling syntax</span></span>

<span data-ttu-id="a7137-195">Шаблоны исключений с `try...with` помощью синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="a7137-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="a7137-196">Согласование функциональности для выполнения перед лицом исключения с сопоставлением шаблонов может быть немного сложнее, если вы хотите сохранить код в чистоте.</span><span class="sxs-lookup"><span data-stu-id="a7137-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="a7137-197">Одним из таких способов обработки этого является использование [активных шаблонов](../language-reference/active-patterns.md) в качестве средства для группирования функциональности, окружающей случай ошибки, за исключением самого.</span><span class="sxs-lookup"><span data-stu-id="a7137-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="a7137-198">Например, вы можете употреблять API, который, когда он бросает исключение, привязав ценную информацию в метаданные исключения.</span><span class="sxs-lookup"><span data-stu-id="a7137-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="a7137-199">Разворачивание полезного значения в теле захваченного исключения внутри Active Pattern и возвращение этого значения может быть полезно в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a7137-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="a7137-200">Не используйте обработку монадических ошибок для замены исключений</span><span class="sxs-lookup"><span data-stu-id="a7137-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="a7137-201">Исключения рассматриваются как несколько табу в функциональном программировании.</span><span class="sxs-lookup"><span data-stu-id="a7137-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="a7137-202">Действительно, исключения нарушают чистоту, поэтому смело считать их не совсем функциональными.</span><span class="sxs-lookup"><span data-stu-id="a7137-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="a7137-203">Однако при этом игнорируется реальность того, где должен работать код, и могут возникать ошибки в времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7137-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="a7137-204">В общем, напишите код на предположении, что большинство вещей не являются ни чистыми, ни полными, чтобы свести к минимуму неприятные сюрпризы.</span><span class="sxs-lookup"><span data-stu-id="a7137-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="a7137-205">Важно учитывать следующие основные сильные стороны/аспекты исключений в отношении их актуальности и целесообразности в режиме выполнения .NET и кросс-языковой экосистеме в целом:</span><span class="sxs-lookup"><span data-stu-id="a7137-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="a7137-206">Они содержат подробную диагностическую информацию, что очень полезно при отладке проблемы.</span><span class="sxs-lookup"><span data-stu-id="a7137-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="a7137-207">Они хорошо понимаются временем выполнения и другими языками .NET.</span><span class="sxs-lookup"><span data-stu-id="a7137-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="a7137-208">Они могут уменьшить значительный шаблон по сравнению с кодом, который выходит из его пути, чтобы *избежать* исключений, реализуя некоторые подмножество их семантики на специальной основе.</span><span class="sxs-lookup"><span data-stu-id="a7137-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="a7137-209">Этот третий пункт имеет решающее значение.</span><span class="sxs-lookup"><span data-stu-id="a7137-209">This third point is critical.</span></span> <span data-ttu-id="a7137-210">Для нетривиальных сложных операций отказ от использования исключений может привести к работе со структурами, подобными этим:</span><span class="sxs-lookup"><span data-stu-id="a7137-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="a7137-211">Что может легко привести к хрупкому коду, как шаблон, соответствующий на "строка-набранных" ошибок:</span><span class="sxs-lookup"><span data-stu-id="a7137-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="a7137-212">Кроме того, может быть заманчиво проглотить любое исключение в желании "простой" функции, которая возвращает "хороший" тип:</span><span class="sxs-lookup"><span data-stu-id="a7137-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="a7137-213">К `tryReadAllText` сожалению, может бросать многочисленные исключения, основанные на множеству вещей, которые могут произойти в файловой системе, и этот код отбрасывает любую информацию о том, что может на самом деле происходит не так в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a7137-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="a7137-214">Если вы замените этот код типом результата, вы вернетесь к разбору сообщений об ошибке с строкой:</span><span class="sxs-lookup"><span data-stu-id="a7137-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="a7137-215">А размещение самого объекта `Error` исключения в конструкторе просто заставляет вас правильно иметь дело с типом исключения на сайте вызова, а не в функции.</span><span class="sxs-lookup"><span data-stu-id="a7137-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="a7137-216">Это эффективно создает проверенные исключения, с которыми, как известно, неинтересно иметь дело в качестве вызываемого API.</span><span class="sxs-lookup"><span data-stu-id="a7137-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="a7137-217">Хорошей альтернативой приведенным выше примерам является уловие *конкретных* исключений и возвращение значимого значения в контексте этого исключения.</span><span class="sxs-lookup"><span data-stu-id="a7137-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="a7137-218">Если вы `tryReadAllText` измените функцию следующим образом, `None` имеет больше смысла:</span><span class="sxs-lookup"><span data-stu-id="a7137-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="a7137-219">Вместо того, чтобы функционировать как универсальный, эта функция теперь будет правильно обрабатывать случай, когда файл не был найден и назначить, что смысл возвращения.</span><span class="sxs-lookup"><span data-stu-id="a7137-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="a7137-220">Это значение возврата может отобразить этот случай ошибки, не отбрасывая при этом какую-либо контекстную информацию или заставляя абонентов иметь дело с случаем, который может не иметь значения на данном этапе кода.</span><span class="sxs-lookup"><span data-stu-id="a7137-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="a7137-221">Такие типы, как, `Result<'Success, 'Error>` подходят для основных операций, где они не вложены, и f'дополнительные типы идеально подходят для представления, когда что-то может либо вернуть *что-то* или *ничего*.</span><span class="sxs-lookup"><span data-stu-id="a7137-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="a7137-222">Однако они не являются заменой исключений и не должны использоваться в попытке заменить исключения.</span><span class="sxs-lookup"><span data-stu-id="a7137-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="a7137-223">Скорее, они должны применяться разумно для рассмотрения конкретных аспектов политики исключения и управления ошибками целевыми способами.</span><span class="sxs-lookup"><span data-stu-id="a7137-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="a7137-224">Частичное применение и программирование без точек</span><span class="sxs-lookup"><span data-stu-id="a7137-224">Partial application and point-free programming</span></span>

<span data-ttu-id="a7137-225">ФЗ поддерживает частичное применение, и, таким образом, различные способы программирования в стиле, свободном от точек.</span><span class="sxs-lookup"><span data-stu-id="a7137-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="a7137-226">Это может быть полезно для повторного использования кода в модуле или реализации чего-либо, но это не то, чтобы разоблачить публично.</span><span class="sxs-lookup"><span data-stu-id="a7137-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="a7137-227">В общем, точечное программирование само по себе не является добродетелью и может добавить значительный когнитивный барьер для людей, которые не погружены в стиль.</span><span class="sxs-lookup"><span data-stu-id="a7137-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="a7137-228">Не используйте частичное применение и карри в публичных AIS</span><span class="sxs-lookup"><span data-stu-id="a7137-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="a7137-229">За небольшим исключением, использование частичного применения в публичных AA может ввести в заблуждение потребителей.</span><span class="sxs-lookup"><span data-stu-id="a7137-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="a7137-230">Как `let`правило, значения, связанные с F-кодом, являются **значениями,** а не **значениями функций.**</span><span class="sxs-lookup"><span data-stu-id="a7137-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="a7137-231">Смешивание значений и значений функций может привести к сохранению небольшого количества строк кода в обмен на `>>` довольно много когнитивных накладных расходов, особенно в сочетании с операторами, такими как для составления функций.</span><span class="sxs-lookup"><span data-stu-id="a7137-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="a7137-232">Рассмотрим инструментарий последствия для программирования без точек</span><span class="sxs-lookup"><span data-stu-id="a7137-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="a7137-233">Карри функции не обозначать свои аргументы.</span><span class="sxs-lookup"><span data-stu-id="a7137-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="a7137-234">Это имеет инструментальный последствия.</span><span class="sxs-lookup"><span data-stu-id="a7137-234">This has tooling implications.</span></span> <span data-ttu-id="a7137-235">Рассмотрим следующие две функции:</span><span class="sxs-lookup"><span data-stu-id="a7137-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="a7137-236">Оба являются действительными `funcWithApplication` функциями, но является функцией карри.</span><span class="sxs-lookup"><span data-stu-id="a7137-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="a7137-237">Когда вы нависнете над их типами в редакторе, вы видите это:</span><span class="sxs-lookup"><span data-stu-id="a7137-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="a7137-238">На сайте вызова, инструменты в инструментарии, такие как Visual Studio `string` `int` не даст вам значимую информацию о том, что и типы ввода на самом деле представляют.</span><span class="sxs-lookup"><span data-stu-id="a7137-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="a7137-239">Если вы сталкиваетесь `funcWithApplication` с кодом, свободным от точек, как это публично расходуется, рекомендуется сделать полное расширение, так что инструментальный инструмент может подобрать на значимые имена для аргументов.</span><span class="sxs-lookup"><span data-stu-id="a7137-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="a7137-240">Кроме того, отладка кода без точек может быть сложной задачей, если не невозможной.</span><span class="sxs-lookup"><span data-stu-id="a7137-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="a7137-241">Инструменты отладки полагаются на значения, `let` связанные с именами (например, привязки), чтобы можно было проверить промежуточные значения в середине выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7137-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="a7137-242">Если код не имеет значений для проверки, отладить нечего.</span><span class="sxs-lookup"><span data-stu-id="a7137-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="a7137-243">В будущем инструменты отладки могут эволюционировать для синтеза этих значений на основе ранее выполненных путей, но не стоит хеджировать свои ставки на *потенциальную* функциональность отладки.</span><span class="sxs-lookup"><span data-stu-id="a7137-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="a7137-244">Рассматривайте частичное применение как метод для уменьшения внутреннего шаблона</span><span class="sxs-lookup"><span data-stu-id="a7137-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="a7137-245">В отличие от предыдущей точки, частичное применение является прекрасным инструментом для уменьшения шаблона внутри приложения или более глубоких внутренностений API.</span><span class="sxs-lookup"><span data-stu-id="a7137-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="a7137-246">Это может быть полезно для модульного тестирования реализации более сложных AIS, где шаблон часто боль иметь дело.</span><span class="sxs-lookup"><span data-stu-id="a7137-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="a7137-247">Например, следующий код показывает, как можно выполнить то, что дает большинство насмешливых инфраструктур, не принимая внешнюю зависимость от такой платформы и не изучая связанный на заказ API.</span><span class="sxs-lookup"><span data-stu-id="a7137-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="a7137-248">Например, рассмотрим следующую топографию решений:</span><span class="sxs-lookup"><span data-stu-id="a7137-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="a7137-249">`ImplementationLogic.fsproj`может подвергать код, такой как:</span><span class="sxs-lookup"><span data-stu-id="a7137-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="a7137-250">Модульное тестирование `Transactions.doTransaction` в `ImplementationLogic.Tests.fsproj` несложно:</span><span class="sxs-lookup"><span data-stu-id="a7137-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="a7137-251">Частичное `doTransaction` применение с насмешливым контекстным объектом позволяет вызывать функцию во всех модульных тестах без необходимости каждый раз создавать насмешливый контекст:</span><span class="sxs-lookup"><span data-stu-id="a7137-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="a7137-252">Этот метод не должен повсеместно применяться ко всей кодовой базе, но это хороший способ уменьшить шаблон для сложных внутренноств и модульного тестирования этих внутренностей.</span><span class="sxs-lookup"><span data-stu-id="a7137-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="a7137-253">Управление доступом</span><span class="sxs-lookup"><span data-stu-id="a7137-253">Access control</span></span>

<span data-ttu-id="a7137-254">ФЗ имеет несколько вариантов [управления доступом,](../language-reference/access-control.md)унаследованных от того, что доступно в времени выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="a7137-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="a7137-255">Они не только использовать для типов - вы можете использовать их для функций, тоже.</span><span class="sxs-lookup"><span data-stu-id="a7137-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="a7137-256">Предпочитаюненее нетипов`public` и членов, пока вам не нужно, чтобы они были публично расходуемыми.</span><span class="sxs-lookup"><span data-stu-id="a7137-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="a7137-257">Это также сводит к минимуму то, что потребители пара.</span><span class="sxs-lookup"><span data-stu-id="a7137-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="a7137-258">Старайтесь сохранить всю `private`функциональность помощника.</span><span class="sxs-lookup"><span data-stu-id="a7137-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="a7137-259">Рассмотрим использование `[<AutoOpen>]` на частный модуль функций помощника, если они становятся многочисленными.</span><span class="sxs-lookup"><span data-stu-id="a7137-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="a7137-260">Выводы типов и дженерики</span><span class="sxs-lookup"><span data-stu-id="a7137-260">Type inference and generics</span></span>

<span data-ttu-id="a7137-261">Вывод типа может спасти вас от ввода большого количества шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a7137-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="a7137-262">Автоматическое обобщение в компиляторе F-й может помочь вам написать более общий код, практически без дополнительных усилий с вашей стороны.</span><span class="sxs-lookup"><span data-stu-id="a7137-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="a7137-263">Тем не менее, эти функции не являются универсально хорошими.</span><span class="sxs-lookup"><span data-stu-id="a7137-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="a7137-264">Рассмотрите маркировку имен аргументов с явными типами в публичных AIS и не опирайтесь на вывод типа для этого.</span><span class="sxs-lookup"><span data-stu-id="a7137-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="a7137-265">Причина этого заключается в том, что **вы** должны контролировать форму вашего API, а не компилятор.</span><span class="sxs-lookup"><span data-stu-id="a7137-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="a7137-266">Хотя компилятор может выполнять прекрасную работу при выводе типов для вас, можно иметь форму изменения API, если внутренние детали, на которые он опирается, изменились.</span><span class="sxs-lookup"><span data-stu-id="a7137-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="a7137-267">Это может быть то, что вы хотите, но это почти наверняка приведет к нарушению Изменения API, что вниз по течению потребители будут иметь дело с.</span><span class="sxs-lookup"><span data-stu-id="a7137-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="a7137-268">Вместо этого, если вы явно контролируете форму вашего общедоступного API, то вы можете контролировать эти изменения.</span><span class="sxs-lookup"><span data-stu-id="a7137-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="a7137-269">С точки зрения DDD, это можно рассматривать как антикоррупционный слой.</span><span class="sxs-lookup"><span data-stu-id="a7137-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="a7137-270">Рассмотрите возможность предоставления значимого названия общим аргументам.</span><span class="sxs-lookup"><span data-stu-id="a7137-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="a7137-271">Если вы не пишете действительно общий код, который не специфичен для конкретного домена, значимое имя может помочь другим программистам понять домен, в который они работают.</span><span class="sxs-lookup"><span data-stu-id="a7137-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="a7137-272">Например, параметр `'Document` типа, названный в контексте взаимодействия с базой данных документов, позволяет понять, что общие типы документов могут быть приняты функцией или членом, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="a7137-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="a7137-273">Рассмотрите вопрос о наименовании общих параметров типа с помощью PascalCase.</span><span class="sxs-lookup"><span data-stu-id="a7137-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="a7137-274">Это общий способ сделать что-то в .NET, поэтому рекомендуется использовать PascalCase, а не snake_case или верблюда.</span><span class="sxs-lookup"><span data-stu-id="a7137-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="a7137-275">Наконец, автоматическое обобщение не всегда является благом для людей, которые являются новыми для F- или большой кодовой базы.</span><span class="sxs-lookup"><span data-stu-id="a7137-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="a7137-276">Существует когнитивных накладных расходов в использовании компонентов, которые являются общими.</span><span class="sxs-lookup"><span data-stu-id="a7137-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="a7137-277">Кроме того, если автоматически обобщенные функции не используются с различными типами ввода (не говоря уже о том, что они предназначены для использования в качестве таковых), то нет никакой реальной пользы для них быть общими в данный момент времени.</span><span class="sxs-lookup"><span data-stu-id="a7137-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="a7137-278">Всегда учитывайте, действительно ли код, который вы пишете, выиграет от общего.</span><span class="sxs-lookup"><span data-stu-id="a7137-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="a7137-279">Производительность</span><span class="sxs-lookup"><span data-stu-id="a7137-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="a7137-280">Предпочитают структуры для небольших типов данных</span><span class="sxs-lookup"><span data-stu-id="a7137-280">Prefer structs for small data types</span></span>

<span data-ttu-id="a7137-281">Использование структур (также называемых типами значений) часто может привести к повышению производительности для некоторых кодов, поскольку обычно он избегает выделения объектов.</span><span class="sxs-lookup"><span data-stu-id="a7137-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="a7137-282">Тем не менее, структуры не всегда являются кнопкой "идти быстрее": если размер данных в структуре превышает 16 байт, копирование данных часто может привести к большему времени процессора тратить, чем с помощью эталонного типа.</span><span class="sxs-lookup"><span data-stu-id="a7137-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="a7137-283">Чтобы определить, следует ли использовать структуру, рассмотрим следующие условия:</span><span class="sxs-lookup"><span data-stu-id="a7137-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="a7137-284">Если размер ваших данных составляет 16 байтов или меньше.</span><span class="sxs-lookup"><span data-stu-id="a7137-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="a7137-285">Если в запущенной программе в памяти может быть много таких типов данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="a7137-286">Если применяется первое условие, обычно следует использовать структуру.</span><span class="sxs-lookup"><span data-stu-id="a7137-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="a7137-287">Если оба применяются, вы должны почти всегда использовать структуру.</span><span class="sxs-lookup"><span data-stu-id="a7137-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="a7137-288">Там могут быть некоторые случаи, когда предыдущие условия применяются, но с помощью структуры не лучше или хуже, чем с помощью эталонного типа, но они могут быть редкими.</span><span class="sxs-lookup"><span data-stu-id="a7137-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="a7137-289">Важно всегда измерять при внесении изменений, как это, хотя, а не работать на предположение или интуицию.</span><span class="sxs-lookup"><span data-stu-id="a7137-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="a7137-290">Предпочитают структурировать tuples при группировке малых типов значений</span><span class="sxs-lookup"><span data-stu-id="a7137-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="a7137-291">Рассмотрим следующие две функции:</span><span class="sxs-lookup"><span data-stu-id="a7137-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="a7137-292">При бенчмарке эти функции со статистическим инструментом бенчмаркинга, как [BenchmarkDotNet](https://benchmarkdotnet.org/), вы обнаружите, что `runWithStructTuple` функция, которая использует структурировать tuples работает на 40% быстрее и не выделяет памяти.</span><span class="sxs-lookup"><span data-stu-id="a7137-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="a7137-293">Однако эти результаты не всегда будут иметь место в вашем собственном коде.</span><span class="sxs-lookup"><span data-stu-id="a7137-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="a7137-294">Если вы пометите функцию как, `inline`код, который использует ссылки tuples может получить некоторые дополнительные оптимизации, или код, который бы выделить может быть просто оптимизирован.</span><span class="sxs-lookup"><span data-stu-id="a7137-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="a7137-295">Вы всегда должны измерять результаты, когда речь идет, и никогда не работать на основе предположения или интуиции.</span><span class="sxs-lookup"><span data-stu-id="a7137-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="a7137-296">Предпочитают записи структурирования, когда тип данных небольшой</span><span class="sxs-lookup"><span data-stu-id="a7137-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="a7137-297">Правило большого пальца, описанное ранее, также имеет место для [типов записей F'.](../language-reference/records.md)</span><span class="sxs-lookup"><span data-stu-id="a7137-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="a7137-298">Рассмотрим следующие типы данных и функции, которые их обрабатывают:</span><span class="sxs-lookup"><span data-stu-id="a7137-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="a7137-299">Это похоже на предыдущий код tuple, но на этот раз пример использует записи и подстроенную внутреннюю функцию.</span><span class="sxs-lookup"><span data-stu-id="a7137-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="a7137-300">При бенчмарке эти функции со статистическим инструментом бенчмаркинга, как [BenchmarkDotNet](https://benchmarkdotnet.org/), вы обнаружите, что `processStructPoint` работает почти на 60% быстрее и ничего не выделяет на управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="a7137-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="a7137-301">Предпочитаю тростковые дискриминируемые союзы, когда тип данных мал</span><span class="sxs-lookup"><span data-stu-id="a7137-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="a7137-302">Предыдущие наблюдения о производительности с структурами tuples и записи также имеет место для [F' Дискриминационные союзы](../language-reference/discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="a7137-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="a7137-303">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="a7137-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="a7137-304">Обычно для моделирования доменов обычно определяются однократные дискриминирующие союзы.</span><span class="sxs-lookup"><span data-stu-id="a7137-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="a7137-305">При бенчмарке эти функции со статистическим инструментом бенчмаркинга, как `reverseName` [BenchmarkDotNet](https://benchmarkdotnet.org/), вы обнаружите, что `structReverseName` работает примерно на 25% быстрее, чем для небольших строк.</span><span class="sxs-lookup"><span data-stu-id="a7137-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="a7137-306">Для больших строк оба выполняют примерно одно и то же.</span><span class="sxs-lookup"><span data-stu-id="a7137-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="a7137-307">Так что, в этом случае, это всегда предпочтительнее использовать структуру.</span><span class="sxs-lookup"><span data-stu-id="a7137-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="a7137-308">Как упоминалось ранее, всегда измерять и не оперировать на предположениях или интуиции.</span><span class="sxs-lookup"><span data-stu-id="a7137-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="a7137-309">Хотя предыдущий пример показал, что структурируемый дискриминируемый союз показал более высокую производительность, при моделировании домена часто бывает больше дискриминированных союзов.</span><span class="sxs-lookup"><span data-stu-id="a7137-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="a7137-310">Более крупные типы данных, подобные этому, могут также выполняться, если они структурируются в зависимости от операций на них, так как может быть задействовано большекопирование.</span><span class="sxs-lookup"><span data-stu-id="a7137-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="a7137-311">Функциональное программирование и мутация</span><span class="sxs-lookup"><span data-stu-id="a7137-311">Functional programming and mutation</span></span>

<span data-ttu-id="a7137-312">Значения F-класса неизменяемы по умолчанию, что позволяет избежать определенных классов ошибок (особенно тех, которые связаны с параллелизмом и параллелизмом).</span><span class="sxs-lookup"><span data-stu-id="a7137-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="a7137-313">Однако в некоторых случаях для достижения оптимальной (или даже разумной) эффективности времени выполнения или распределения памяти, промежуток работы может быть лучше всего реализован с помощью мутации состояния на месте.</span><span class="sxs-lookup"><span data-stu-id="a7137-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="a7137-314">Это возможно в основе выбора с F `mutable` с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="a7137-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="a7137-315">Использование `mutable` в F-фз может противоречить функциональной чистоте.</span><span class="sxs-lookup"><span data-stu-id="a7137-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="a7137-316">Это понятно, но функциональная чистота везде может противоречить целям производительности.</span><span class="sxs-lookup"><span data-stu-id="a7137-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="a7137-317">Компромисс заключается в том, чтобы инкапсулировать мутации таким образом, что абоненты не должны заботиться о том, что происходит, когда они называют функцию.</span><span class="sxs-lookup"><span data-stu-id="a7137-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="a7137-318">Это позволяет написать функциональный интерфейс над реализацией на основе мутаций для критически важного кода.</span><span class="sxs-lookup"><span data-stu-id="a7137-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="a7137-319">Оберните изменяемый код в неизменяемые интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a7137-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="a7137-320">При основе референтной прозрачности в качестве цели крайне важно писать код, который не разоблачает изменяемые подбрюшье критически важных функций.</span><span class="sxs-lookup"><span data-stu-id="a7137-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="a7137-321">Например, следующий код `Array.contains` реализует функцию в основной библиотеке F-кода:</span><span class="sxs-lookup"><span data-stu-id="a7137-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="a7137-322">Вызов этой функции несколько раз не изменяет базовый массив, и не требует, чтобы вы поддерживали любое изменяемое состояние в его потреблении.</span><span class="sxs-lookup"><span data-stu-id="a7137-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="a7137-323">Он является референциально прозрачным, хотя почти каждая строка кода в нем использует мутацию.</span><span class="sxs-lookup"><span data-stu-id="a7137-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="a7137-324">Рассмотрим инкапсуляцию изменяемых данных в классах</span><span class="sxs-lookup"><span data-stu-id="a7137-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="a7137-325">В предыдущем примере использовалась одна функция для инкапсулировать операции с использованием изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="a7137-326">Этого не всегда достаточно для более сложных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="a7137-327">Рассмотрим следующие наборы функций:</span><span class="sxs-lookup"><span data-stu-id="a7137-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="a7137-328">Этот код выполняется, но он предоставляет структуру данных, основанную на мутации, которую абоненты несут ответственность за поддержание.</span><span class="sxs-lookup"><span data-stu-id="a7137-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="a7137-329">Это может быть обернуто внутри класса без каких-либо основных членов, которые могут измениться:</span><span class="sxs-lookup"><span data-stu-id="a7137-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="a7137-330">`Closure1Table`инкапсулирует базовую структуру данных на основе мутаций, тем самым не заставляя абонентов поддерживать базовую структуру данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="a7137-331">Классы — это мощный способ инкапсулировать данные и процедуры, основанные на мутациях, не подвергая детали абонентам.</span><span class="sxs-lookup"><span data-stu-id="a7137-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="a7137-332">Предпочитаю `let mutable` эталонные ячейки</span><span class="sxs-lookup"><span data-stu-id="a7137-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="a7137-333">Справочные ячейки являются способом представления ссылки на значение, а не само значение.</span><span class="sxs-lookup"><span data-stu-id="a7137-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="a7137-334">Хотя они могут быть использованы для критически важного кода, они не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="a7137-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="a7137-335">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="a7137-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="a7137-336">Использование справочной ячейки теперь "загрязняет" весь последующий код, имея необходимость dereference и перессылки базовых данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="a7137-337">Вместо этого, рассмотрим: `let mutable`</span><span class="sxs-lookup"><span data-stu-id="a7137-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="a7137-338">Помимо одной точки мутации в середине выражения лямбда, `acc` все другие коды, которые касаются может `let`сделать это таким образом, что ничем не отличается от использования нормального связанного неизменного значения.</span><span class="sxs-lookup"><span data-stu-id="a7137-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="a7137-339">Это упростит изменение с течением времени.</span><span class="sxs-lookup"><span data-stu-id="a7137-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="a7137-340">Программирование объектов</span><span class="sxs-lookup"><span data-stu-id="a7137-340">Object programming</span></span>

<span data-ttu-id="a7137-341">ФЗ имеет полную поддержку объектов и объектно-ориентированных (OO) концепций.</span><span class="sxs-lookup"><span data-stu-id="a7137-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="a7137-342">Хотя многие концепции OO являются мощными и полезными, не все из них идеально подходят для использования.</span><span class="sxs-lookup"><span data-stu-id="a7137-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="a7137-343">Следующие списки содержат рекомендации по категориям функций OO на высоком уровне.</span><span class="sxs-lookup"><span data-stu-id="a7137-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="a7137-344">**Рассмотрите возможность использования этих функций во многих ситуациях:**</span><span class="sxs-lookup"><span data-stu-id="a7137-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="a7137-345">Точка нотации (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="a7137-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="a7137-346">Члены инстанции</span><span class="sxs-lookup"><span data-stu-id="a7137-346">Instance members</span></span>
* <span data-ttu-id="a7137-347">Неявные конструкторы</span><span class="sxs-lookup"><span data-stu-id="a7137-347">Implicit constructors</span></span>
* <span data-ttu-id="a7137-348">Статические члены</span><span class="sxs-lookup"><span data-stu-id="a7137-348">Static members</span></span>
* <span data-ttu-id="a7137-349">Показательное обозначение (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="a7137-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="a7137-350">Именованные и факультативные аргументы</span><span class="sxs-lookup"><span data-stu-id="a7137-350">Named and Optional arguments</span></span>
* <span data-ttu-id="a7137-351">Интерфейсы и реализации интерфейсов</span><span class="sxs-lookup"><span data-stu-id="a7137-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="a7137-352">**Не достигайте этих функций во-первых, но разумно применять их, когда они удобны для решения проблемы:**</span><span class="sxs-lookup"><span data-stu-id="a7137-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="a7137-353">Перегрузка методов</span><span class="sxs-lookup"><span data-stu-id="a7137-353">Method overloading</span></span>
* <span data-ttu-id="a7137-354">Инкапсулированные изменяемые данные</span><span class="sxs-lookup"><span data-stu-id="a7137-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="a7137-355">Операторы по типам</span><span class="sxs-lookup"><span data-stu-id="a7137-355">Operators on types</span></span>
* <span data-ttu-id="a7137-356">Автосвойства</span><span class="sxs-lookup"><span data-stu-id="a7137-356">Auto properties</span></span>
* <span data-ttu-id="a7137-357">Реализация `IDisposable` и`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="a7137-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="a7137-358">Расширение типа</span><span class="sxs-lookup"><span data-stu-id="a7137-358">Type extensions</span></span>
* <span data-ttu-id="a7137-359">События</span><span class="sxs-lookup"><span data-stu-id="a7137-359">Events</span></span>
* <span data-ttu-id="a7137-360">Структуры</span><span class="sxs-lookup"><span data-stu-id="a7137-360">Structs</span></span>
* <span data-ttu-id="a7137-361">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a7137-361">Delegates</span></span>
* <span data-ttu-id="a7137-362">Перечисления</span><span class="sxs-lookup"><span data-stu-id="a7137-362">Enums</span></span>

<span data-ttu-id="a7137-363">**Как правило, избегайте этих функций, если вы не должны использовать их:**</span><span class="sxs-lookup"><span data-stu-id="a7137-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="a7137-364">Иерархии типов наследования и наследования наследования</span><span class="sxs-lookup"><span data-stu-id="a7137-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="a7137-365">Нутс и`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="a7137-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="a7137-366">Предпочитаю состав над наследством</span><span class="sxs-lookup"><span data-stu-id="a7137-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="a7137-367">[Композиция над наследством](https://en.wikipedia.org/wiki/Composition_over_inheritance) – это давняя идиома, к которым может придерживаться хороший код F'.</span><span class="sxs-lookup"><span data-stu-id="a7137-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="a7137-368">Фундаментальный принцип заключается в том, что вы не должны подвергать базовый класс и заставить абонентов наследовать из этого базового класса, чтобы получить функциональность.</span><span class="sxs-lookup"><span data-stu-id="a7137-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="a7137-369">Используйте выражения объектов для реализации интерфейсов, если вам не нужен класс</span><span class="sxs-lookup"><span data-stu-id="a7137-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="a7137-370">[Выражения объектов](../language-reference/object-expressions.md) позволяют реализовывать интерфейсы на лету, связывая реализованный интерфейс с значением без необходимости делать это внутри класса.</span><span class="sxs-lookup"><span data-stu-id="a7137-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="a7137-371">Это удобно, особенно если вам _нужно только_ реализовать интерфейс и не нужно для полного класса.</span><span class="sxs-lookup"><span data-stu-id="a7137-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="a7137-372">Например, вот код, который работает в [Ionide,](http://ionide.io/) чтобы обеспечить действие исправления кода, `open` если вы добавили символ, для которого у вас нет оператора:</span><span class="sxs-lookup"><span data-stu-id="a7137-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="a7137-373">Поскольку при взаимодействии с API Visual Studio не требуется, выражения объектов являются идеальным инструментом для этого.</span><span class="sxs-lookup"><span data-stu-id="a7137-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="a7137-374">Они также ценны для модульного тестирования, когда вы хотите заглушить интерфейс с тестовыми процедурами в специальной манере.</span><span class="sxs-lookup"><span data-stu-id="a7137-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="a7137-375">Рассмотрим аббревиатуры типа для сокращения подписей</span><span class="sxs-lookup"><span data-stu-id="a7137-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="a7137-376">[Аббревиативы типа](../language-reference/type-abbreviations.md) — это удобный способ присвоить метку другому типу, например подпись функции или более сложный тип.</span><span class="sxs-lookup"><span data-stu-id="a7137-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="a7137-377">Например, следующий псевдоним присваивает метку тому, что необходимо для определения вычислений с [помощью CNTK,](https://docs.microsoft.com/cognitive-toolkit/)библиотеки глубокого обучения:</span><span class="sxs-lookup"><span data-stu-id="a7137-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="a7137-378">Имя `Computation` является удобным способом обозначить любую функцию, которая соответствует подписи, которую он псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a7137-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="a7137-379">Использование таких аббревиатив типа удобно и позволяет использовать более краткий код.</span><span class="sxs-lookup"><span data-stu-id="a7137-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="a7137-380">Избегайте использования аббревиаций типа для представления вашего домена</span><span class="sxs-lookup"><span data-stu-id="a7137-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="a7137-381">Хотя аббревиатуры типа удобны для придания имени для функциональных подписей, они могут ввести в заблуждение при сокращении других типов.</span><span class="sxs-lookup"><span data-stu-id="a7137-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="a7137-382">Рассмотрим эту аббревиаюрацию:</span><span class="sxs-lookup"><span data-stu-id="a7137-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="a7137-383">Это может ввести в заблуждение несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="a7137-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="a7137-384">`BufferSize`это не абстракция; это просто другое название для рядов.</span><span class="sxs-lookup"><span data-stu-id="a7137-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="a7137-385">Если `BufferSize` он разоблачается в общедоступном API, его `int`можно легко неправильно истолковать как нечто большее, чем просто.</span><span class="sxs-lookup"><span data-stu-id="a7137-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="a7137-386">Как правило, типы доменов имеют несколько `int`атрибутов к ним и не являются примитивными типами, как.</span><span class="sxs-lookup"><span data-stu-id="a7137-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="a7137-387">Эта аббревиатива нарушает это предположение.</span><span class="sxs-lookup"><span data-stu-id="a7137-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="a7137-388">Корпус `BufferSize` (PascalCase) подразумевает, что этот тип содержит больше данных.</span><span class="sxs-lookup"><span data-stu-id="a7137-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="a7137-389">Этот псевдоним не предлагает повышенной ясности по сравнению с предоставлением названного аргумента к функции.</span><span class="sxs-lookup"><span data-stu-id="a7137-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="a7137-390">Аббревиатива не проявляется в скомпилированном IL; это всего лишь целый ряд, и этот псевдоним представляет собой построение компиляции времени.</span><span class="sxs-lookup"><span data-stu-id="a7137-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="a7137-391">Таким образом, ловушка с типом Abbreviations является то, что они **не** являются абстракциями по сравнению с типами, которые они аббревиании.</span><span class="sxs-lookup"><span data-stu-id="a7137-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="a7137-392">В предыдущем примере, `BufferSize` `int` это просто под крышкой, без каких-либо дополнительных данных, ни каких-либо преимуществ от системы типа, кроме того, что `int` уже есть.</span><span class="sxs-lookup"><span data-stu-id="a7137-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="a7137-393">Альтернативный подход к использованию аббревиатий типов для представления домена заключается в использовании единичных дискриминируемых союзов.</span><span class="sxs-lookup"><span data-stu-id="a7137-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="a7137-394">Предыдущий образец можно смоделировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a7137-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="a7137-395">Если вы пишете код, `BufferSize` который работает с точки зрения и его основное значение, вам нужно построить один, а не пройти в любой произвольной ряд:</span><span class="sxs-lookup"><span data-stu-id="a7137-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="a7137-396">Это снижает вероятность ошибочного прохождения произвольного `send` стеге в функцию, поскольку абонент должен построить `BufferSize` тип, чтобы обернуть значение перед вызовом функции.</span><span class="sxs-lookup"><span data-stu-id="a7137-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
