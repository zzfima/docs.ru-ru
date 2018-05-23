---
title: Статически разрешаемые параметры типа (F#)
description: 'Сведения об использовании языка F # статически разрешаемый параметр типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.'
ms.date: 05/16/2016
ms.openlocfilehash: 12c2af4d9df7ae1e5e77efc9413eb8777459a83c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="f12b8-103">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="f12b8-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="f12b8-104">Объект *статически разрешаемый параметр типа* является параметром типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f12b8-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="f12b8-105">Они предваряются символом крышки (^).</span><span class="sxs-lookup"><span data-stu-id="f12b8-105">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="f12b8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f12b8-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="f12b8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f12b8-107">Remarks</span></span>
<span data-ttu-id="f12b8-108">В языке F # существует два различных типа параметров типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="f12b8-109">Первый тип — Стандартная универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="f12b8-110">Такие параметры обозначаются апостроф ('), как и в `'T` и `'U`.</span><span class="sxs-lookup"><span data-stu-id="f12b8-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="f12b8-111">Они эквивалентны параметров универсального типа в других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f12b8-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="f12b8-112">Статически разрешаемые другого типа и обозначается символом крышки, как в `^T` и `^U`.</span><span class="sxs-lookup"><span data-stu-id="f12b8-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="f12b8-113">Статически разрешаемые параметры типа, в первую очередь используются в связи с ограничениями членов, которые являются ограничения, которые позволяют указать, что аргумент типа должен иметь определенный элемент или элементы для использования.</span><span class="sxs-lookup"><span data-stu-id="f12b8-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="f12b8-114">Нет возможности для создания такого типа ограничения с помощью обычного универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="f12b8-115">В следующей таблице перечислены сходства и различия между двумя типами параметров типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="f12b8-116">Функция</span><span class="sxs-lookup"><span data-stu-id="f12b8-116">Feature</span></span>|<span data-ttu-id="f12b8-117">Универсальный</span><span class="sxs-lookup"><span data-stu-id="f12b8-117">Generic</span></span>|<span data-ttu-id="f12b8-118">Статически разрешаемые</span><span class="sxs-lookup"><span data-stu-id="f12b8-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="f12b8-119">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f12b8-119">Syntax</span></span>|<span data-ttu-id="f12b8-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="f12b8-120">`'T`, `'U`</span></span>|<span data-ttu-id="f12b8-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="f12b8-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="f12b8-122">Время разрешения</span><span class="sxs-lookup"><span data-stu-id="f12b8-122">Resolution time</span></span>|<span data-ttu-id="f12b8-123">Выполнение</span><span class="sxs-lookup"><span data-stu-id="f12b8-123">Run time</span></span>|<span data-ttu-id="f12b8-124">Время компиляции</span><span class="sxs-lookup"><span data-stu-id="f12b8-124">Compile time</span></span>|
|<span data-ttu-id="f12b8-125">Ограничения элементов</span><span class="sxs-lookup"><span data-stu-id="f12b8-125">Member constraints</span></span>|<span data-ttu-id="f12b8-126">Не может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="f12b8-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="f12b8-127">Может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="f12b8-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="f12b8-128">Создание кода</span><span class="sxs-lookup"><span data-stu-id="f12b8-128">Code generation</span></span>|<span data-ttu-id="f12b8-129">Тип (или метод) со стандартными параметрами универсального типа приводит к формированию одного универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="f12b8-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="f12b8-130">Создаются несколько экземпляров типов и методов, для каждого типа, который нужно.</span><span class="sxs-lookup"><span data-stu-id="f12b8-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="f12b8-131">Использование с типами</span><span class="sxs-lookup"><span data-stu-id="f12b8-131">Use with types</span></span>|<span data-ttu-id="f12b8-132">Может использоваться с типами.</span><span class="sxs-lookup"><span data-stu-id="f12b8-132">Can be used on types.</span></span>|<span data-ttu-id="f12b8-133">Не может использоваться с типами.</span><span class="sxs-lookup"><span data-stu-id="f12b8-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="f12b8-134">Использование со встроенными функциями</span><span class="sxs-lookup"><span data-stu-id="f12b8-134">Use with inline functions</span></span>|<span data-ttu-id="f12b8-135">Нет.</span><span class="sxs-lookup"><span data-stu-id="f12b8-135">No.</span></span> <span data-ttu-id="f12b8-136">Встроенная функция не может быть параметризовано с параметром standard универсального типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="f12b8-137">Да.</span><span class="sxs-lookup"><span data-stu-id="f12b8-137">Yes.</span></span> <span data-ttu-id="f12b8-138">Статически разрешаемые параметры типа нельзя использовать в функции или методы, не являющиеся встроенными.</span><span class="sxs-lookup"><span data-stu-id="f12b8-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="f12b8-139">Многие основные функции библиотеки F #, особенно операторы статически разрешаемые параметры типов.</span><span class="sxs-lookup"><span data-stu-id="f12b8-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="f12b8-140">Эти функции и операторы в строке и привести к созданию эффективного кода для численных вычислений.</span><span class="sxs-lookup"><span data-stu-id="f12b8-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="f12b8-141">Встроенные методы и функции, использующие операторы или использовать другие функции, которые статически разрешаемые параметры типов, можно также использовать статически разрешаемые параметры типа самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f12b8-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="f12b8-142">Часто такие встроенные функции, имеющие статически разрешаемые параметры типа определяются определение типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="f12b8-143">В следующем примере показано определение оператора, который определяется содержат параметр статически разрешаемые типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="f12b8-144">Разрешить тип `(+@)` основан на использование обоих `(+)` и `(*)`, оба из благодаря чему вывод типа ограничениям членов на статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="f12b8-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="f12b8-145">Разрешенный тип, как показано в интерпретатору F #, будет следующим.</span><span class="sxs-lookup"><span data-stu-id="f12b8-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="f12b8-146">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f12b8-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="f12b8-147">Начиная с версии 4.1 F # можно также указать имена конкретных типов в сигнатурах статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="f12b8-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="f12b8-148">В предыдущих версиях языка имя типа могут быть выведены фактически компилятором, но фактически не удается задать в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="f12b8-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="f12b8-149">Начиная с F # 4.1 можно также указать имена конкретных типов в сигнатурах статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="f12b8-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="f12b8-150">Ниже приведен пример:</span><span class="sxs-lookup"><span data-stu-id="f12b8-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f12b8-151">См. также</span><span class="sxs-lookup"><span data-stu-id="f12b8-151">See Also</span></span>
[<span data-ttu-id="f12b8-152">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f12b8-152">Generics</span></span>](index.md)

[<span data-ttu-id="f12b8-153">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="f12b8-153">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="f12b8-154">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="f12b8-154">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="f12b8-155">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f12b8-155">Constraints</span></span>](constraints.md)

[<span data-ttu-id="f12b8-156">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="f12b8-156">Inline Functions</span></span>](../functions/inline-functions.md)
