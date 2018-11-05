---
title: Расширения типов (F#)
description: 'Узнайте, как разрешить расширения типов F #, добавлять новые члены в ранее определенный тип объекта.'
ms.date: 07/20/2018
ms.openlocfilehash: 27238db1fd0803f62c32755fbc4ab7688f5c107e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43874983"
---
# <a name="type-extensions"></a><span data-ttu-id="f1246-103">Расширения типов</span><span class="sxs-lookup"><span data-stu-id="f1246-103">Type extensions</span></span>

<span data-ttu-id="f1246-104">Расширения типа (также называется _дополнения_) — это семейство функций, которые позволяют добавлять новые члены в ранее определенный тип объекта.</span><span class="sxs-lookup"><span data-stu-id="f1246-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="f1246-105">Ниже перечислены три возможности.</span><span class="sxs-lookup"><span data-stu-id="f1246-105">The three features are:</span></span>

* <span data-ttu-id="f1246-106">Встроенных расширений типа</span><span class="sxs-lookup"><span data-stu-id="f1246-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="f1246-107">В дополнительных расширениях</span><span class="sxs-lookup"><span data-stu-id="f1246-107">Optional type extensions</span></span>
* <span data-ttu-id="f1246-108">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="f1246-108">Extension methods</span></span>

<span data-ttu-id="f1246-109">Каждый может использоваться в различных сценариях и имеет различные компромиссы.</span><span class="sxs-lookup"><span data-stu-id="f1246-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1246-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1246-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="f1246-111">Встроенных расширений типа</span><span class="sxs-lookup"><span data-stu-id="f1246-111">Intrinsic type extensions</span></span>

<span data-ttu-id="f1246-112">Встроенное расширение типа является расширением типа, который расширяет определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="f1246-113">Встроенных расширений типа должен быть определен в том же файле **и** в том же пространстве имен или модуль в качестве типа, они расширяемых.</span><span class="sxs-lookup"><span data-stu-id="f1246-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="f1246-114">Все другие определения приведет к их, [дополнительных расширениях](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="f1246-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="f1246-115">Встроенных расширений типа иногда являются более точный способ отделяют функции из объявления типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="f1246-116">В следующем примере показано, как определить встроенное расширение типа:</span><span class="sxs-lookup"><span data-stu-id="f1246-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="f1246-117">С помощью расширения типа позволяет отделить каждое из перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="f1246-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="f1246-118">Объявление `Variant` типа</span><span class="sxs-lookup"><span data-stu-id="f1246-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="f1246-119">Функциональные возможности для печати `Variant` класс в зависимости от его «фигуры»</span><span class="sxs-lookup"><span data-stu-id="f1246-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="f1246-120">Способ доступа к функциональность печати с помощью стиля объекта `.`-нотация</span><span class="sxs-lookup"><span data-stu-id="f1246-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="f1246-121">Это является альтернативой для определения всех объектов, как член на `Variant`.</span><span class="sxs-lookup"><span data-stu-id="f1246-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="f1246-122">Несмотря на то, что он не является по своей сути эффективнее, он может быть очистки представлением функциональные возможности, в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="f1246-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="f1246-123">Встроенных расширений типа компилируются как члены типа, они дополнения и типа отображаются при проверке этого типа с путем отражения.</span><span class="sxs-lookup"><span data-stu-id="f1246-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="f1246-124">В дополнительных расширениях</span><span class="sxs-lookup"><span data-stu-id="f1246-124">Optional type extensions</span></span>

<span data-ttu-id="f1246-125">Необязательный тип расширения — это расширение, которое находится за пределами исходного модуля, пространства имен или сборке расширяемого типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="f1246-126">В дополнительных расширениях полезны для расширения типа, который вы не определили самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f1246-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="f1246-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="f1246-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="f1246-128">Теперь вы можете открывать `RepeatElements` как, если он является членом <xref:System.Collections.Generic.IEnumerable%601> , пока `Extensions` модуль открыт в области, в которой вы работаете.</span><span class="sxs-lookup"><span data-stu-id="f1246-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="f1246-129">Дополнительные расширения не отображаются в расширенном типе при проверке с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="f1246-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="f1246-130">Дополнительное расширение должно содержаться в модулях, и они только в области, когда модуль, содержащий его модуль открыт или область — в противном случае.</span><span class="sxs-lookup"><span data-stu-id="f1246-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="f1246-131">Члены дополнительных расширений компилируются в статические члены, для которых экземпляр объекта неявно передается как первый параметр.</span><span class="sxs-lookup"><span data-stu-id="f1246-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="f1246-132">Тем не менее они действуют как будто они являются членами экземпляра или статические члены в соответствии с, как они определены.</span><span class="sxs-lookup"><span data-stu-id="f1246-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="f1246-133">Ограничение универсального типа встроенных и необязательных расширений</span><span class="sxs-lookup"><span data-stu-id="f1246-133">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="f1246-134">Можно объявить в расширение типа для универсального типа, где переменной типа ограничен.</span><span class="sxs-lookup"><span data-stu-id="f1246-134">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="f1246-135">Требование относится, что ограничение объявления расширение соответствует ограничению объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-135">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="f1246-136">Тем не менее даже в том случае, если ограничения сопоставляются между объявленным типом и расширение типа, это возможно для ограничения могут выводиться в теле расширенный элемент, который накладывает различные требование параметра типа, чем объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-136">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="f1246-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="f1246-137">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="f1246-138">Не существует способа получить этот код для работы с расширением необязательный тип:</span><span class="sxs-lookup"><span data-stu-id="f1246-138">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="f1246-139">Как, `Sum` член имеет различные ограничения `'T` (`static member get_Zero` и `static member (+)`), чем то, что определяет расширение типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-139">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="f1246-140">Изменение расширения типа иметь такое же ограничение как `Sum` больше не будут соответствовать определенные ограничения на `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="f1246-140">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="f1246-141">Создание, изменение члена `member inline Sum` вызывает эту ошибку, что ограничения типов совпадают</span><span class="sxs-lookup"><span data-stu-id="f1246-141">Making changing the member to `member inline Sum` will give an error that type constraints are mismatched</span></span>

<span data-ttu-id="f1246-142">Что требуется являются статических методов, которые могут быть представлены так, как если бы они расширение типа «float в пространстве».</span><span class="sxs-lookup"><span data-stu-id="f1246-142">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="f1246-143">Это, где методы расширения возникает необходимость.</span><span class="sxs-lookup"><span data-stu-id="f1246-143">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="f1246-144">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="f1246-144">Extension methods</span></span>

<span data-ttu-id="f1246-145">Наконец методы расширения (иногда называется «расширение члены стиля C#») могут быть объявлены в F # метод статический член класса.</span><span class="sxs-lookup"><span data-stu-id="f1246-145">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="f1246-146">Методы расширения полезны для когда нужно определять расширения на универсальный тип, который будет ограничивать тип переменной.</span><span class="sxs-lookup"><span data-stu-id="f1246-146">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="f1246-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="f1246-147">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="f1246-148">При использовании этого кода поможет вам отображаются так, как если `Sum` определен на <xref:System.Collections.Generic.IEnumerable%601>, при условии что `Extensions` был открыт или находится в области.</span><span class="sxs-lookup"><span data-stu-id="f1246-148">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="f1246-149">Другие примечания</span><span class="sxs-lookup"><span data-stu-id="f1246-149">Other remarks</span></span>

<span data-ttu-id="f1246-150">Расширения типов также иметь следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="f1246-150">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="f1246-151">Любой тип, который может осуществляться можно расширить.</span><span class="sxs-lookup"><span data-stu-id="f1246-151">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="f1246-152">Можно определить внутренние и необязательный тип расширения _любой_ тип члена, не только методы.</span><span class="sxs-lookup"><span data-stu-id="f1246-152">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="f1246-153">Поэтому свойства расширения возможны также, например.</span><span class="sxs-lookup"><span data-stu-id="f1246-153">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="f1246-154">`self-identifier` Маркера в [синтаксис](type-extensions.md#syntax) представляет экземпляр типа, вызываемого так же, как обычные элементы.</span><span class="sxs-lookup"><span data-stu-id="f1246-154">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="f1246-155">Расширенные элементы могут быть статическими или члены экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f1246-155">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="f1246-156">Переменные типа в расширении типа должны соответствовать ограничениям объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="f1246-156">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="f1246-157">Для расширения типов также имеются следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="f1246-157">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="f1246-158">Тип расширения не поддерживают виртуальные и абстрактные методы.</span><span class="sxs-lookup"><span data-stu-id="f1246-158">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="f1246-159">Тип расширения не поддерживают методы переопределения в качестве дополнения.</span><span class="sxs-lookup"><span data-stu-id="f1246-159">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="f1246-160">Тип расширения не поддерживают [статически разрешаемые параметры типов](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f1246-160">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="f1246-161">Необязательный тип расширения не поддерживают конструкторы в качестве дополнения.</span><span class="sxs-lookup"><span data-stu-id="f1246-161">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="f1246-162">Расширения типов нельзя определить для [аббревиатуры типов](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="f1246-162">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="f1246-163">Тип расширения не являются допустимыми для `byref<'T>` (хотя они могут быть объявлены).</span><span class="sxs-lookup"><span data-stu-id="f1246-163">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="f1246-164">Расширения типов не допускаются для атрибутов (хотя они могут быть объявлены).</span><span class="sxs-lookup"><span data-stu-id="f1246-164">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="f1246-165">Можно определять расширения, которые перегружать другие методы с тем же именем, но компилятор F # отдает предпочтение методам, не являющийся расширением методы при возникновении неоднозначного вызова.</span><span class="sxs-lookup"><span data-stu-id="f1246-165">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="f1246-166">Наконец Если для одного типа имеется несколько встроенных расширений типа, все члены должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="f1246-166">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="f1246-167">Для дополнительных расширениях члены различных расширений типов в тот же тип может иметь одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="f1246-167">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="f1246-168">Ошибок неоднозначности возникают, только в том случае, если код клиента открывает две различные области, определяющие одинаковые имена членов.</span><span class="sxs-lookup"><span data-stu-id="f1246-168">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1246-169">См. также</span><span class="sxs-lookup"><span data-stu-id="f1246-169">See also</span></span>

- [<span data-ttu-id="f1246-170">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f1246-170">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f1246-171">Члены</span><span class="sxs-lookup"><span data-stu-id="f1246-171">Members</span></span>](members/index.md)
