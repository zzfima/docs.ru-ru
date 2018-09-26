---
title: Статически разрешаемые параметры типа (F#)
description: 'Сведения об использовании F # статически разрешаемым параметром типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.'
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087269"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="c63d6-103">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="c63d6-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="c63d6-104">Объект *статически разрешаемым параметром типа* является параметром типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c63d6-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="c63d6-105">Перед ними присутствует символ крышки (^).</span><span class="sxs-lookup"><span data-stu-id="c63d6-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="c63d6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c63d6-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="c63d6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c63d6-107">Remarks</span></span>

<span data-ttu-id="c63d6-108">В языке F # существует два вида параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="c63d6-109">Первый тип — стандартным параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="c63d6-110">Они обозначаются с помощью апострофа ('), как показано на `'T` и `'U`.</span><span class="sxs-lookup"><span data-stu-id="c63d6-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="c63d6-111">Они эквивалентны параметров универсального типа в других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c63d6-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="c63d6-112">Другой вид является статически разрешаемым и обозначается символом крышки, как показано на `^T` и `^U`.</span><span class="sxs-lookup"><span data-stu-id="c63d6-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="c63d6-113">Статически разрешаемые параметры типа, в основном используются в связи с ограничениями членов, которые являются ограничения, которые позволяют пользователю указать, что аргумент типа должен иметь определенный элемент или элементы для использования.</span><span class="sxs-lookup"><span data-stu-id="c63d6-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="c63d6-114">Нет способа для создания такого рода ограничение с помощью параметра регулярных универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="c63d6-115">В следующей таблице перечислены сходства и различия между двумя типами параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="c63d6-116">Функция</span><span class="sxs-lookup"><span data-stu-id="c63d6-116">Feature</span></span>|<span data-ttu-id="c63d6-117">Универсальный</span><span class="sxs-lookup"><span data-stu-id="c63d6-117">Generic</span></span>|<span data-ttu-id="c63d6-118">Статически разрешаемые</span><span class="sxs-lookup"><span data-stu-id="c63d6-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="c63d6-119">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c63d6-119">Syntax</span></span>|<span data-ttu-id="c63d6-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="c63d6-120">`'T`, `'U`</span></span>|<span data-ttu-id="c63d6-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="c63d6-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="c63d6-122">Время разрешения</span><span class="sxs-lookup"><span data-stu-id="c63d6-122">Resolution time</span></span>|<span data-ttu-id="c63d6-123">Выполнение</span><span class="sxs-lookup"><span data-stu-id="c63d6-123">Run time</span></span>|<span data-ttu-id="c63d6-124">Время компиляции</span><span class="sxs-lookup"><span data-stu-id="c63d6-124">Compile time</span></span>|
|<span data-ttu-id="c63d6-125">Ограничения члена</span><span class="sxs-lookup"><span data-stu-id="c63d6-125">Member constraints</span></span>|<span data-ttu-id="c63d6-126">Не может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="c63d6-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="c63d6-127">Может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="c63d6-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="c63d6-128">Создание кода</span><span class="sxs-lookup"><span data-stu-id="c63d6-128">Code generation</span></span>|<span data-ttu-id="c63d6-129">Тип (или метод) со стандартными параметрами универсального типа приводит к формированию, одного универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="c63d6-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="c63d6-130">Создаются несколько экземпляров типов и методов, он будет необходим для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="c63d6-131">Использовать с типами</span><span class="sxs-lookup"><span data-stu-id="c63d6-131">Use with types</span></span>|<span data-ttu-id="c63d6-132">Можно применять к типам.</span><span class="sxs-lookup"><span data-stu-id="c63d6-132">Can be used on types.</span></span>|<span data-ttu-id="c63d6-133">Нельзя применять к типам.</span><span class="sxs-lookup"><span data-stu-id="c63d6-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="c63d6-134">Использование со встроенными функциями</span><span class="sxs-lookup"><span data-stu-id="c63d6-134">Use with inline functions</span></span>|<span data-ttu-id="c63d6-135">Нет.</span><span class="sxs-lookup"><span data-stu-id="c63d6-135">No.</span></span> <span data-ttu-id="c63d6-136">Встроенная функция не могут быть параметризованы с параметром standard универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="c63d6-137">Да.</span><span class="sxs-lookup"><span data-stu-id="c63d6-137">Yes.</span></span> <span data-ttu-id="c63d6-138">Статически разрешаемые параметры типа нельзя применять к функции или методы, не являющиеся встроенными.</span><span class="sxs-lookup"><span data-stu-id="c63d6-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="c63d6-139">Многие функции F # core библиотеки, особенно операторы, статически разрешаемые параметры типов.</span><span class="sxs-lookup"><span data-stu-id="c63d6-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="c63d6-140">Эти функции и операторы в строке и привести к созданию эффективного кода для численных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c63d6-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="c63d6-141">Встроенные методы и функции, которые используют операторы или использовать другие функции, которые статически разрешаемые параметры типов, также могут использовать статически разрешаемые параметры типа самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c63d6-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="c63d6-142">Часто такие встроенные функции, имеющие статически разрешаемые параметры типа определяются вывод типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="c63d6-143">В следующем примере показано определение оператора, логически распознается статически разрешаемым параметром типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="c63d6-144">Разрешенный тип `(+@)` основан на использование обоих `(+)` и `(*)`, обе из чему вывод типа ограничениям членов на статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="c63d6-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="c63d6-145">Разрешенный тип, как показано в интерпретаторе F #, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c63d6-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="c63d6-146">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c63d6-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="c63d6-147">Начиная с F # 4.1, можно также указать имена конкретный тип в статически разрешенный тип параметра сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="c63d6-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="c63d6-148">В предыдущих версиях языка имя типа могут быть выведены фактически компилятором, но фактически не удается задать в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="c63d6-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="c63d6-149">По состоянию на F # 4.1 можно также указать имена конкретный тип в статически разрешенный тип параметра сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="c63d6-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="c63d6-150">Ниже приведен пример:</span><span class="sxs-lookup"><span data-stu-id="c63d6-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="c63d6-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c63d6-151">See also</span></span>

- [<span data-ttu-id="c63d6-152">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="c63d6-152">Generics</span></span>](index.md)
- [<span data-ttu-id="c63d6-153">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="c63d6-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="c63d6-154">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="c63d6-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="c63d6-155">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c63d6-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="c63d6-156">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="c63d6-156">Inline Functions</span></span>](../functions/inline-functions.md)
