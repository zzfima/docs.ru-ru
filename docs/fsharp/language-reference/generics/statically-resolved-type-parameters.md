---
title: Статически разрешаемые параметры типов
description: Узнайте, как использовать F# статически разрешаемый параметр типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.
ms.date: 05/16/2016
ms.openlocfilehash: 43ed79b6e5f43a499a27b05e26472b021c455e44
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630593"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="27bd2-103">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="27bd2-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="27bd2-104">*Статически разрешаемый параметр типа* — это параметр типа, который заменяется фактическим типом во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="27bd2-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="27bd2-105">Им предшествует символ каретки (^).</span><span class="sxs-lookup"><span data-stu-id="27bd2-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="27bd2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27bd2-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="27bd2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="27bd2-107">Remarks</span></span>

<span data-ttu-id="27bd2-108">На F# языке существует два различных вида параметров типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="27bd2-109">Первый тип является стандартным параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="27bd2-110">Они обозначаются апострофом ('), как в `'T` и `'U`.</span><span class="sxs-lookup"><span data-stu-id="27bd2-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="27bd2-111">Они эквивалентны параметрам универсального типа в других .NET Framework языках.</span><span class="sxs-lookup"><span data-stu-id="27bd2-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="27bd2-112">Другой тип является статически разрешаемым и обозначается символом курсора, как в `^T` и `^U`.</span><span class="sxs-lookup"><span data-stu-id="27bd2-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="27bd2-113">Статически разрешаемые параметры типа в первую очередь полезны в сочетании с ограничениями элементов, которые являются ограничениями, позволяющими указать, что аргумент типа должен иметь определенный элемент или элементы для использования.</span><span class="sxs-lookup"><span data-stu-id="27bd2-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="27bd2-114">Невозможно создать этот тип ограничения с помощью обычного параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="27bd2-115">В следующей таблице перечислены сходства и различия между двумя типами параметров типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="27bd2-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="27bd2-116">Feature</span></span>|<span data-ttu-id="27bd2-117">Универсальный</span><span class="sxs-lookup"><span data-stu-id="27bd2-117">Generic</span></span>|<span data-ttu-id="27bd2-118">Статическое разрешение</span><span class="sxs-lookup"><span data-stu-id="27bd2-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="27bd2-119">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27bd2-119">Syntax</span></span>|<span data-ttu-id="27bd2-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="27bd2-120">`'T`, `'U`</span></span>|<span data-ttu-id="27bd2-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="27bd2-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="27bd2-122">Время разрешения</span><span class="sxs-lookup"><span data-stu-id="27bd2-122">Resolution time</span></span>|<span data-ttu-id="27bd2-123">Выполнение</span><span class="sxs-lookup"><span data-stu-id="27bd2-123">Run time</span></span>|<span data-ttu-id="27bd2-124">Время компиляции</span><span class="sxs-lookup"><span data-stu-id="27bd2-124">Compile time</span></span>|
|<span data-ttu-id="27bd2-125">Ограничения элементов</span><span class="sxs-lookup"><span data-stu-id="27bd2-125">Member constraints</span></span>|<span data-ttu-id="27bd2-126">Не может использоваться с ограничениями элементов.</span><span class="sxs-lookup"><span data-stu-id="27bd2-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="27bd2-127">Может использоваться с ограничениями элементов.</span><span class="sxs-lookup"><span data-stu-id="27bd2-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="27bd2-128">Создание кода</span><span class="sxs-lookup"><span data-stu-id="27bd2-128">Code generation</span></span>|<span data-ttu-id="27bd2-129">Тип (или метод) со стандартными параметрами универсального типа приводит к созданию одного универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="27bd2-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="27bd2-130">Создается несколько экземпляров типов и методов, по одному для каждого требуемого типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="27bd2-131">Использование с типами</span><span class="sxs-lookup"><span data-stu-id="27bd2-131">Use with types</span></span>|<span data-ttu-id="27bd2-132">Может использоваться для типов.</span><span class="sxs-lookup"><span data-stu-id="27bd2-132">Can be used on types.</span></span>|<span data-ttu-id="27bd2-133">Не может использоваться для типов.</span><span class="sxs-lookup"><span data-stu-id="27bd2-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="27bd2-134">Использование со встроенными функциями</span><span class="sxs-lookup"><span data-stu-id="27bd2-134">Use with inline functions</span></span>|<span data-ttu-id="27bd2-135">Нет.</span><span class="sxs-lookup"><span data-stu-id="27bd2-135">No.</span></span> <span data-ttu-id="27bd2-136">Встроенная функция не может быть параметризована со стандартным параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="27bd2-137">Да.</span><span class="sxs-lookup"><span data-stu-id="27bd2-137">Yes.</span></span> <span data-ttu-id="27bd2-138">Статически разрешаемые параметры типа нельзя использовать в функциях и методах, которые не являются встроенными.</span><span class="sxs-lookup"><span data-stu-id="27bd2-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="27bd2-139">Многие F# функции основной библиотеки, в частности, операторы, имеют статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="27bd2-140">Эти функции и операторы являются встроенными и приводят к эффективному созданию кода для числовых вычислений.</span><span class="sxs-lookup"><span data-stu-id="27bd2-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="27bd2-141">Встроенные методы и функции, использующие операторы, или другие функции, которые имеют статически разрешаемые параметры типа, также могут использовать статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="27bd2-142">Как правило, вывод типа выводит такие встроенные функции в статически разрешаемые параметры типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="27bd2-143">В следующем примере показано определение оператора, для которого определен статически разрешаемый параметр типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="27bd2-144">Разрешенный тип `(+@)` основан на использовании обоих `(+)` параметров и `(*)`, которые вызывают вывод типа для определения ограничений членов в статически разрешаемых параметрах типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="27bd2-145">Разрешенный тип, как показано в F# интерпретаторе, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="27bd2-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="27bd2-146">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="27bd2-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="27bd2-147">Начиная с F# 4,1, можно также указать конкретные имена типов в статически разрешаемых сигнатурах параметров типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="27bd2-148">В предыдущих версиях языка имя типа может быть выделено компилятором, но фактически не может быть указано в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="27bd2-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="27bd2-149">Начиная с F# 4,1 можно также указать конкретные имена типов в статически разрешаемых сигнатурах параметров типа.</span><span class="sxs-lookup"><span data-stu-id="27bd2-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="27bd2-150">Ниже приведен пример:</span><span class="sxs-lookup"><span data-stu-id="27bd2-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="27bd2-151">См. также</span><span class="sxs-lookup"><span data-stu-id="27bd2-151">See also</span></span>

- [<span data-ttu-id="27bd2-152">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="27bd2-152">Generics</span></span>](index.md)
- [<span data-ttu-id="27bd2-153">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="27bd2-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="27bd2-154">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="27bd2-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="27bd2-155">Ограничения</span><span class="sxs-lookup"><span data-stu-id="27bd2-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="27bd2-156">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="27bd2-156">Inline Functions</span></span>](../functions/inline-functions.md)
