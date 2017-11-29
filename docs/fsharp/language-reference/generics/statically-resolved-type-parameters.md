---
title: "Статически разрешаемые параметры типа (F#)"
description: "Сведения об использовании языка F # статически разрешаемый параметр типа, который заменяется фактическим типом во время компиляции, а не во время выполнения."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b3797415-3e49-4f8a-a8ee-fa614c5721aa
ms.openlocfilehash: 88b4590a4323e75949c1915503b51793283792de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="c9db3-104">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="c9db3-104">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="c9db3-105">Объект *статически разрешаемый параметр типа* является параметром типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9db3-105">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="c9db3-106">Они предваряются символом крышки (^).</span><span class="sxs-lookup"><span data-stu-id="c9db3-106">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="c9db3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9db3-107">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="c9db3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9db3-108">Remarks</span></span>
<span data-ttu-id="c9db3-109">В языке F # существует два различных типа параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-109">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="c9db3-110">Первый тип — Стандартная универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-110">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="c9db3-111">Такие параметры обозначаются апостроф ('), как и в `'T` и `'U`.</span><span class="sxs-lookup"><span data-stu-id="c9db3-111">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="c9db3-112">Они эквивалентны параметров универсального типа в других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9db3-112">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="c9db3-113">Статически разрешаемые другого типа и обозначается символом крышки, как в `^T` и `^U`.</span><span class="sxs-lookup"><span data-stu-id="c9db3-113">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="c9db3-114">Статически разрешаемые параметры типа, в первую очередь используются в связи с ограничениями членов, которые являются ограничения, которые позволяют указать, что аргумент типа должен иметь определенный элемент или элементы для использования.</span><span class="sxs-lookup"><span data-stu-id="c9db3-114">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="c9db3-115">Нет возможности для создания такого типа ограничения с помощью обычного универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-115">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="c9db3-116">В следующей таблице перечислены сходства и различия между двумя типами параметров типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-116">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="c9db3-117">Функция</span><span class="sxs-lookup"><span data-stu-id="c9db3-117">Feature</span></span>|<span data-ttu-id="c9db3-118">Универсальный</span><span class="sxs-lookup"><span data-stu-id="c9db3-118">Generic</span></span>|<span data-ttu-id="c9db3-119">Статически разрешаемые</span><span class="sxs-lookup"><span data-stu-id="c9db3-119">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="c9db3-120">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9db3-120">Syntax</span></span>|<span data-ttu-id="c9db3-121">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="c9db3-121">`'T`, `'U`</span></span>|<span data-ttu-id="c9db3-122">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="c9db3-122">`^T`, `^U`</span></span>|
|<span data-ttu-id="c9db3-123">Время разрешения</span><span class="sxs-lookup"><span data-stu-id="c9db3-123">Resolution time</span></span>|<span data-ttu-id="c9db3-124">Выполнение</span><span class="sxs-lookup"><span data-stu-id="c9db3-124">Run time</span></span>|<span data-ttu-id="c9db3-125">Время компиляции</span><span class="sxs-lookup"><span data-stu-id="c9db3-125">Compile time</span></span>|
|<span data-ttu-id="c9db3-126">Ограничения элементов</span><span class="sxs-lookup"><span data-stu-id="c9db3-126">Member constraints</span></span>|<span data-ttu-id="c9db3-127">Не может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="c9db3-127">Cannot be used with member constraints.</span></span>|<span data-ttu-id="c9db3-128">Может использоваться с ограничениями членов.</span><span class="sxs-lookup"><span data-stu-id="c9db3-128">Can be used with member constraints.</span></span>|
|<span data-ttu-id="c9db3-129">Создание кода</span><span class="sxs-lookup"><span data-stu-id="c9db3-129">Code generation</span></span>|<span data-ttu-id="c9db3-130">Тип (или метод) со стандартными параметрами универсального типа приводит к формированию одного универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="c9db3-130">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="c9db3-131">Создаются несколько экземпляров типов и методов, для каждого типа, который нужно.</span><span class="sxs-lookup"><span data-stu-id="c9db3-131">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="c9db3-132">Использование с типами</span><span class="sxs-lookup"><span data-stu-id="c9db3-132">Use with types</span></span>|<span data-ttu-id="c9db3-133">Может использоваться с типами.</span><span class="sxs-lookup"><span data-stu-id="c9db3-133">Can be used on types.</span></span>|<span data-ttu-id="c9db3-134">Не может использоваться с типами.</span><span class="sxs-lookup"><span data-stu-id="c9db3-134">Cannot be used on types.</span></span>|
|<span data-ttu-id="c9db3-135">Использование со встроенными функциями</span><span class="sxs-lookup"><span data-stu-id="c9db3-135">Use with inline functions</span></span>|<span data-ttu-id="c9db3-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="c9db3-136">No.</span></span> <span data-ttu-id="c9db3-137">Встроенная функция не может быть параметризовано с параметром standard универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-137">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="c9db3-138">Да.</span><span class="sxs-lookup"><span data-stu-id="c9db3-138">Yes.</span></span> <span data-ttu-id="c9db3-139">Статически разрешаемые параметры типа нельзя использовать в функции или методы, не являющиеся встроенными.</span><span class="sxs-lookup"><span data-stu-id="c9db3-139">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="c9db3-140">Многие основные функции библиотеки F #, особенно операторы статически разрешаемые параметры типов.</span><span class="sxs-lookup"><span data-stu-id="c9db3-140">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="c9db3-141">Эти функции и операторы в строке и привести к созданию эффективного кода для численных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c9db3-141">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="c9db3-142">Встроенные методы и функции, использующие операторы или использовать другие функции, которые статически разрешаемые параметры типов, можно также использовать статически разрешаемые параметры типа самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c9db3-142">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="c9db3-143">Часто такие встроенные функции, имеющие статически разрешаемые параметры типа определяются определение типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-143">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="c9db3-144">В следующем примере показано определение оператора, который определяется содержат параметр статически разрешаемые типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-144">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="c9db3-145">Разрешить тип `(+@)` основан на использование обоих `(+)` и `(*)`, оба из благодаря чему вывод типа ограничениям членов на статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="c9db3-145">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="c9db3-146">Разрешенный тип, как показано в интерпретатору F #, будет следующим.</span><span class="sxs-lookup"><span data-stu-id="c9db3-146">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member (+) : ^a * ^b -> ^d) and
(^a or ^c) : (static member (+) : ^a * ^c -> ^b)
```

<span data-ttu-id="c9db3-147">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c9db3-147">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="c9db3-148">Начиная с версии 4.1 F # можно также указать имена конкретных типов в сигнатурах статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="c9db3-148">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="c9db3-149">В предыдущих версиях языка имя типа могут быть выведены фактически компилятором, но фактически не удается задать в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="c9db3-149">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="c9db3-150">Начиная с F # 4.1 можно также указать имена конкретных типов в сигнатурах статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="c9db3-150">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="c9db3-151">Ниже приведен пример:</span><span class="sxs-lookup"><span data-stu-id="c9db3-151">Here's an example:</span></span>

```fsharp
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

## <a name="see-also"></a><span data-ttu-id="c9db3-152">См. также</span><span class="sxs-lookup"><span data-stu-id="c9db3-152">See Also</span></span>
[<span data-ttu-id="c9db3-153">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="c9db3-153">Generics</span></span>](index.md)

[<span data-ttu-id="c9db3-154">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="c9db3-154">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="c9db3-155">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="c9db3-155">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="c9db3-156">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c9db3-156">Constraints</span></span>](constraints.md)

[<span data-ttu-id="c9db3-157">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="c9db3-157">Inline Functions</span></span>](../functions/inline-functions.md)
