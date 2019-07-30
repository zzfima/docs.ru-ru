---
title: Вывод типа
description: Узнайте, как F# компилятор определяет типы значений, переменных, параметров и возвращаемых значений.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630182"
---
# <a name="type-inference"></a><span data-ttu-id="170d3-103">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="170d3-103">Type Inference</span></span>

<span data-ttu-id="170d3-104">В F# этом разделе описывается, как компилятор определяет типы значений, переменных, параметров и возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="170d3-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="170d3-105">Определение типа в целом</span><span class="sxs-lookup"><span data-stu-id="170d3-105">Type Inference in General</span></span>

<span data-ttu-id="170d3-106">Идея определения типа заключается в том, что нет необходимости указывать типы F# конструкций, за исключением случаев, когда компилятор не может вывести тип.</span><span class="sxs-lookup"><span data-stu-id="170d3-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="170d3-107">Пропуск сведений о явном типе не означает, F# что является динамически типизированным языком или что значения F# в слабо типизированы.</span><span class="sxs-lookup"><span data-stu-id="170d3-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="170d3-108">F#— Это язык со статической типизацией, который означает, что компилятор выводит точный тип для каждой конструкции во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="170d3-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="170d3-109">Если у компилятора недостаточно сведений для вывода типов каждой конструкции, необходимо предоставить дополнительные сведения о типе, как правило, путем добавления явных заметок типа в любое место кода.</span><span class="sxs-lookup"><span data-stu-id="170d3-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="170d3-110">Вывод типов параметров и возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="170d3-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="170d3-111">В списке параметров не нужно указывать тип каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="170d3-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="170d3-112">И, тем F# не менее, является языком со статической типизацией, поэтому во время компиляции каждое значение и выражение имеют определенный тип.</span><span class="sxs-lookup"><span data-stu-id="170d3-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="170d3-113">Для тех типов, которые не указываются явным образом, компилятор выводит тип на основе контекста.</span><span class="sxs-lookup"><span data-stu-id="170d3-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="170d3-114">Если тип не указан иным образом, он выводится как универсальный.</span><span class="sxs-lookup"><span data-stu-id="170d3-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="170d3-115">Если код использует несогласованное значение, таким образом, что не существует единственного выводимого типа, удовлетворяющего всем условиям использования значения, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="170d3-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="170d3-116">Тип возвращаемого значения функции определяется типом последнего выражения в функции.</span><span class="sxs-lookup"><span data-stu-id="170d3-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="170d3-117">Например, `a` в следующем коде типы параметров и `b` и возвращаемый тип выводятся `int` так, что литерал `100` имеет тип `int`.</span><span class="sxs-lookup"><span data-stu-id="170d3-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="170d3-118">Можно повлиять на вывод типа, изменив литералы.</span><span class="sxs-lookup"><span data-stu-id="170d3-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="170d3-119">Если сделать `100` a `u` `b` ,добавив`a`суффикс, типы`uint32`, и возвращаемое значение будут выведены как. `uint32`</span><span class="sxs-lookup"><span data-stu-id="170d3-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="170d3-120">Также можно повлиять на вывод типа с помощью других конструкций, которые подразумевают ограничения на тип, например функции и методы, работающие только с определенным типом.</span><span class="sxs-lookup"><span data-stu-id="170d3-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="170d3-121">Кроме того, можно применить явные аннотации типа к параметрам функции или метода или переменным в выражениях, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="170d3-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="170d3-122">Ошибки возникают при возникновении конфликтов между разными ограничениями.</span><span class="sxs-lookup"><span data-stu-id="170d3-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="170d3-123">Можно также явно указать возвращаемое значение функции, указав аннотацию типа после всех параметров.</span><span class="sxs-lookup"><span data-stu-id="170d3-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="170d3-124">Типичный случай, когда аннотация типа полезен для параметра, — это то, что параметр является типом объекта и требуется использовать член.</span><span class="sxs-lookup"><span data-stu-id="170d3-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="170d3-125">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="170d3-125">Automatic Generalization</span></span>

<span data-ttu-id="170d3-126">Если код функции не зависит от типа параметра, компилятор считает, что параметр является универсальным.</span><span class="sxs-lookup"><span data-stu-id="170d3-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="170d3-127">Это называется *автоматической*обобщением и может быть мощным средством для написания универсального кода без повышения сложности.</span><span class="sxs-lookup"><span data-stu-id="170d3-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="170d3-128">Например, следующая функция объединяет два параметра любого типа в кортеж.</span><span class="sxs-lookup"><span data-stu-id="170d3-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="170d3-129">Тип выводится как</span><span class="sxs-lookup"><span data-stu-id="170d3-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="170d3-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="170d3-130">Additional Information</span></span>

<span data-ttu-id="170d3-131">Определение типа описывается более подробно в спецификации F# языка.</span><span class="sxs-lookup"><span data-stu-id="170d3-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="170d3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="170d3-132">See also</span></span>

- [<span data-ttu-id="170d3-133">Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="170d3-133">Automatic Generalization</span></span>](./generics/automatic-generalization.md)
