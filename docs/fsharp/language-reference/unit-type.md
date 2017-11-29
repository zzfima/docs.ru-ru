---
title: "Тип Unit (F#)"
description: "Узнайте, как тип «unit» F # часто используется для хранения на месте, где требуется значение с помощью синтаксиса языка при необходимости или требуемого нет значения."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: eabbb6d7-80f3-4fa5-80b4-0f48982466a7
ms.openlocfilehash: 60ac08c0e3f8380a8f9dec7a083ede93c68bb0e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="unit-type"></a><span data-ttu-id="322c7-104">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="322c7-104">Unit Type</span></span>

<span data-ttu-id="322c7-105">`unit` Тип является типом, указывает на отсутствие конкретного значения; `unit` тип имеет только одно значение, который выступает в качестве заполнителя, если никакое другое значение не существует, или требуется.</span><span class="sxs-lookup"><span data-stu-id="322c7-105">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="322c7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="322c7-106">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="322c7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="322c7-107">Remarks</span></span>
<span data-ttu-id="322c7-108">Каждый F # выражение должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="322c7-108">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="322c7-109">Для выражений, не создающих значение, которое представляет интерес, значение типа `unit` используется.</span><span class="sxs-lookup"><span data-stu-id="322c7-109">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="322c7-110">`unit` Тип напоминает `void` типа в языках, таких как C# и C++.</span><span class="sxs-lookup"><span data-stu-id="322c7-110">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="322c7-111">`unit` Тип имеет одно значение, и это значение обозначается токеном `()`.</span><span class="sxs-lookup"><span data-stu-id="322c7-111">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="322c7-112">Значение `unit` типа часто используется в F #, отмечающая, где требуется значение с помощью синтаксиса языка, но в том случае, когда значение не требуется или требуемого программирования.</span><span class="sxs-lookup"><span data-stu-id="322c7-112">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="322c7-113">Примером может служить возвращаемое значение `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="322c7-113">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="322c7-114">Поскольку важные действия `printf` выполнение операции в функции, функции не обязательно возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="322c7-114">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="322c7-115">Таким образом, возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="322c7-115">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="322c7-116">Некоторые конструкции ожидают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="322c7-116">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="322c7-117">Например `do` привязки или код на верхнем уровне модуля является ожидаемым результатом вычисления `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="322c7-117">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="322c7-118">Компилятор создает предупреждение при `do` привязки или код на верхнем уровне модуля дает результат, отличный от `unit` значение, которое не используется, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="322c7-118">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="322c7-119">Это предупреждение — это характеристика, функционального программирования; он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="322c7-119">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="322c7-120">В классическом функциональном программировании, где функции не имеют никаких побочных эффектов, конечное возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="322c7-120">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="322c7-121">Таким образом Если результат учитывается, он является возможной ошибки программирования.</span><span class="sxs-lookup"><span data-stu-id="322c7-121">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="322c7-122">Хотя F # не является чисто функциональным языком программирования, рекомендуется выполнить в стиле функционального программирования по возможности.</span><span class="sxs-lookup"><span data-stu-id="322c7-122">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="322c7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="322c7-123">See Also</span></span>
[<span data-ttu-id="322c7-124">Примитив</span><span class="sxs-lookup"><span data-stu-id="322c7-124">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="322c7-125">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="322c7-125">F# Language Reference</span></span>](index.md)
