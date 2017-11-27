---
title: "Вывод типа (F#)"
description: "Узнайте, как компилятор F # определяет типы значений, переменных, параметров и возвращаемых значений."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2d5fa4b1-732a-4d71-a62d-07f7ee79fe06
ms.openlocfilehash: c23954c0a0828cc7d2aae0553d37d5ee1dfbe152
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-inference"></a><span data-ttu-id="22f09-104">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="22f09-104">Type Inference</span></span>

<span data-ttu-id="22f09-105">В этом разделе описывается, как компилятор F # определяет типы значений, переменных, параметров и возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="22f09-105">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="22f09-106">Определение типа в целом</span><span class="sxs-lookup"><span data-stu-id="22f09-106">Type Inference in General</span></span>
<span data-ttu-id="22f09-107">Концепция вывода типа является не имеют для указания типов конструкций F #, за исключением случаев, когда компилятор не может определить тип.</span><span class="sxs-lookup"><span data-stu-id="22f09-107">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="22f09-108">Пропуск сведения явный тип означает, что F # — это динамически типизированный язык или что значения в языке F # слабо типизированы.</span><span class="sxs-lookup"><span data-stu-id="22f09-108">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="22f09-109">F # — это статически типизированный язык, это означает, что компилятор выводит точный тип, для каждой конструкции во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="22f09-109">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="22f09-110">Если имеется достаточно сведений, чтобы компилятор мог вывести типы каждой конструкции, вы должны предоставить дополнительные сведения о типе, обычно путем добавления заметок явный тип, где-либо в коде.</span><span class="sxs-lookup"><span data-stu-id="22f09-110">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="22f09-111">Вывод параметров и возвращаемые типы</span><span class="sxs-lookup"><span data-stu-id="22f09-111">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="22f09-112">В списке параметров не нужно указать тип каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="22f09-112">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="22f09-113">И еще, F # — это статически типизированный язык, и поэтому каждое значение и выражение имеют определенный тип во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="22f09-113">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="22f09-114">Для этих типов, которые явно не указан компилятор выводит тип, в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="22f09-114">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="22f09-115">Если тип не указана иным образом, он определяется как универсальные.</span><span class="sxs-lookup"><span data-stu-id="22f09-115">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="22f09-116">Если код использует значение несогласованно, так что нет единственного выведенного типа, который удовлетворяет всем вариантам использования значения, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="22f09-116">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="22f09-117">Тип возвращаемого значения функции определяется по типу последнего выражения в функции.</span><span class="sxs-lookup"><span data-stu-id="22f09-117">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="22f09-118">Например, в следующем коде, типы параметров `a` и `b` и тип возвращаемого значения выводятся быть `int` так как литерал `100` относится к типу `int`.</span><span class="sxs-lookup"><span data-stu-id="22f09-118">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="22f09-119">Может повлиять на вывод типа, изменив литералы.</span><span class="sxs-lookup"><span data-stu-id="22f09-119">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="22f09-120">При внесении `100` `uint32` путем добавления суффикса `u`, типы `a`, `b`, и имеют тип возвращаемого значения `uint32`.</span><span class="sxs-lookup"><span data-stu-id="22f09-120">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="22f09-121">Также могут повлиять на определение типа, используя другие конструкции, которые подразумевают ограничения на типы, такие как функции и методы, работающие с определенным типом.</span><span class="sxs-lookup"><span data-stu-id="22f09-121">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="22f09-122">Кроме того можно применить явный тип заметки для параметров функции или метода или переменные в выражениях, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="22f09-122">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="22f09-123">Если возникают конфликты между различными ограничениями возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="22f09-123">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="22f09-124">Вы также можно явно указать возвращаемое значение функции, предоставляя аннотацию типа после того как все параметры.</span><span class="sxs-lookup"><span data-stu-id="22f09-124">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="22f09-125">Распространенный случай, когда полезно аннотации типа для параметра — параметр не является типом объекта, если необходимо использовать член.</span><span class="sxs-lookup"><span data-stu-id="22f09-125">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="22f09-126">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="22f09-126">Automatic Generalization</span></span>
<span data-ttu-id="22f09-127">Если код функции не зависит от типа параметра, компилятор считает, что параметр является универсальным.</span><span class="sxs-lookup"><span data-stu-id="22f09-127">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="22f09-128">Это называется *Автоматическое обобщение*, и он может быть помогать при написании универсального кода без повышения сложности.</span><span class="sxs-lookup"><span data-stu-id="22f09-128">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="22f09-129">Например следующая функция объединяет два параметра любого типа в кортеж.</span><span class="sxs-lookup"><span data-stu-id="22f09-129">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="22f09-130">Тип определяется как</span><span class="sxs-lookup"><span data-stu-id="22f09-130">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="22f09-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="22f09-131">Additional Information</span></span>
<span data-ttu-id="22f09-132">Определение типа является более подробно в спецификации языка F #.</span><span class="sxs-lookup"><span data-stu-id="22f09-132">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="22f09-133">См. также</span><span class="sxs-lookup"><span data-stu-id="22f09-133">See Also</span></span>
[<span data-ttu-id="22f09-134">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="22f09-134">Automatic Generalization</span></span>](generics/automatic-generalization.md)
