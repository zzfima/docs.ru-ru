---
title: Вывод типа
description: Узнайте, как F# компилятор определяет типы значений, переменных, параметров и возвращаемых значений.
ms.date: 05/16/2016
ms.openlocfilehash: ab1a4aa8df4312287df749d5d6d0ea2858091152
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641679"
---
# <a name="type-inference"></a><span data-ttu-id="6a881-103">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="6a881-103">Type Inference</span></span>

<span data-ttu-id="6a881-104">Здесь описывается, как F# компилятор определяет типы значений, переменных, параметров и возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="6a881-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="6a881-105">Определение типа в целом</span><span class="sxs-lookup"><span data-stu-id="6a881-105">Type Inference in General</span></span>

<span data-ttu-id="6a881-106">Вывод типа суть в том, что у вас нет позволяет указать типы F# конструкции, за исключением случаев, когда компилятор не может определить тип.</span><span class="sxs-lookup"><span data-stu-id="6a881-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="6a881-107">Пропуск явные сведения о типах не означает, что F# — динамически типизированный язык или значений в F# являются нестрого типизированными.</span><span class="sxs-lookup"><span data-stu-id="6a881-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="6a881-108">F#— Это статически типизированный язык, это означает, что компилятор выводит тип точное, для каждой конструкции во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="6a881-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="6a881-109">Если имеется достаточно информации для компилятору команду выведения типов каждой конструкции, необходимо предоставить дополнительные сведения о типе, обычно путем добавления явные обозначения типов, где-нибудь в коде.</span><span class="sxs-lookup"><span data-stu-id="6a881-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="6a881-110">Определение параметров и возвращаемых типов</span><span class="sxs-lookup"><span data-stu-id="6a881-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="6a881-111">В списке параметров у вас нет для указания типа каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="6a881-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="6a881-112">И еще, F# — это статически типизированный язык, и поэтому каждое значение и выражение имеет определенный тип во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="6a881-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="6a881-113">Для этих типов, которые явно не указан компилятор выводит тип на основе контекста.</span><span class="sxs-lookup"><span data-stu-id="6a881-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="6a881-114">Если тип не указан, он определяется как универсальный.</span><span class="sxs-lookup"><span data-stu-id="6a881-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="6a881-115">Если код использует значение несогласованно, так что нет единственного выведенного типа, который удовлетворяет все случаи использования значения, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6a881-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="6a881-116">Тип возвращаемого значения функции определяется типа последнего выражения в функции.</span><span class="sxs-lookup"><span data-stu-id="6a881-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="6a881-117">Например, в следующем коде, типы параметров `a` и `b` и тип возвращаемого значения определяется как `int` так как литерал `100` имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="6a881-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="6a881-118">Вывод типа, можно изменить, изменив литералы.</span><span class="sxs-lookup"><span data-stu-id="6a881-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="6a881-119">При внесении `100` `uint32` путем добавления суффикса `u`, типы `a`, `b`, и возвращаемое значение имеют тип `uint32`.</span><span class="sxs-lookup"><span data-stu-id="6a881-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="6a881-120">Может также повлиять на определение типа с помощью других конструкций, которые подразумевают ограничения на типы, такие как функции и методы, которые работают с определенным типом.</span><span class="sxs-lookup"><span data-stu-id="6a881-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="6a881-121">Кроме того можно применять явные обозначения типов для параметров функции или метода или для переменных в выражениях, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6a881-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="6a881-122">Если возникают конфликты между различными ограничениями возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="6a881-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="6a881-123">Можно явным образом указать возвращаемое значение функции, предоставляя аннотацию типа в конце концов параметры.</span><span class="sxs-lookup"><span data-stu-id="6a881-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="6a881-124">Распространенный случай, где аннотацию типа полезен для параметра, когда параметр не является типом объекта и вы хотите использовать член.</span><span class="sxs-lookup"><span data-stu-id="6a881-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="6a881-125">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="6a881-125">Automatic Generalization</span></span>

<span data-ttu-id="6a881-126">Если код функции не зависит от типа параметра, компилятор считает, что параметр является универсальным.</span><span class="sxs-lookup"><span data-stu-id="6a881-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="6a881-127">Это называется *Автоматическое обобщение*, и может быть помогать при написании универсального кода без повышения сложности.</span><span class="sxs-lookup"><span data-stu-id="6a881-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="6a881-128">Например следующая функция объединяет два параметра любого типа в кортеж.</span><span class="sxs-lookup"><span data-stu-id="6a881-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="6a881-129">Тип определяется как</span><span class="sxs-lookup"><span data-stu-id="6a881-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="6a881-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6a881-130">Additional Information</span></span>

<span data-ttu-id="6a881-131">Вывод типа описан более подробно в F# спецификации языка.</span><span class="sxs-lookup"><span data-stu-id="6a881-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a881-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6a881-132">See also</span></span>

- [<span data-ttu-id="6a881-133">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="6a881-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
