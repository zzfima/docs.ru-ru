---
title: Тип Unit (F#)
description: 'Узнайте, как тип «unit» F # часто используется для хранения на месте, где требуется значение с помощью синтаксиса языка при необходимости или требуемого нет значения.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1a8c8f74e31c5426a9fb6a7143e9d2ac9a7104c0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="unit-type"></a><span data-ttu-id="895a3-103">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="895a3-103">Unit Type</span></span>

<span data-ttu-id="895a3-104">`unit` Тип является типом, указывает на отсутствие конкретного значения; `unit` тип имеет только одно значение, который выступает в качестве заполнителя, если никакое другое значение не существует, или требуется.</span><span class="sxs-lookup"><span data-stu-id="895a3-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="895a3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="895a3-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="895a3-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="895a3-106">Remarks</span></span>
<span data-ttu-id="895a3-107">Каждый F # выражение должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="895a3-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="895a3-108">Для выражений, не создающих значение, которое представляет интерес, значение типа `unit` используется.</span><span class="sxs-lookup"><span data-stu-id="895a3-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="895a3-109">`unit` Тип напоминает `void` типа в языках, таких как C# и C++.</span><span class="sxs-lookup"><span data-stu-id="895a3-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="895a3-110">`unit` Тип имеет одно значение, и это значение обозначается токеном `()`.</span><span class="sxs-lookup"><span data-stu-id="895a3-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="895a3-111">Значение `unit` типа часто используется в F #, отмечающая, где требуется значение с помощью синтаксиса языка, но в том случае, когда значение не требуется или требуемого программирования.</span><span class="sxs-lookup"><span data-stu-id="895a3-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="895a3-112">Примером может служить возвращаемое значение `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="895a3-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="895a3-113">Поскольку важные действия `printf` выполнение операции в функции, функции не обязательно возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="895a3-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="895a3-114">Таким образом, возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="895a3-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="895a3-115">Некоторые конструкции ожидают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="895a3-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="895a3-116">Например `do` привязки или код на верхнем уровне модуля является ожидаемым результатом вычисления `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="895a3-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="895a3-117">Компилятор создает предупреждение при `do` привязки или код на верхнем уровне модуля дает результат, отличный от `unit` значение, которое не используется, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="895a3-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="895a3-118">Это предупреждение — это характеристика, функционального программирования; он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="895a3-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="895a3-119">В классическом функциональном программировании, где функции не имеют никаких побочных эффектов, конечное возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="895a3-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="895a3-120">Таким образом Если результат учитывается, он является возможной ошибки программирования.</span><span class="sxs-lookup"><span data-stu-id="895a3-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="895a3-121">Хотя F # не является чисто функциональным языком программирования, рекомендуется выполнить в стиле функционального программирования по возможности.</span><span class="sxs-lookup"><span data-stu-id="895a3-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="895a3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="895a3-122">See Also</span></span>
[<span data-ttu-id="895a3-123">Примитив</span><span class="sxs-lookup"><span data-stu-id="895a3-123">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="895a3-124">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="895a3-124">F# Language Reference</span></span>](index.md)
