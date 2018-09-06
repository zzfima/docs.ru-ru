---
title: Тип Unit (F#)
description: 'Узнайте, как тип «unit» F # часто используется для хранения в место, где требуется значение с помощью синтаксиса языка Если значение не является вам.'
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773439"
---
# <a name="unit-type"></a><span data-ttu-id="68f92-103">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="68f92-103">Unit Type</span></span>

<span data-ttu-id="68f92-104">`unit` Тип является типом, который указывает на отсутствие конкретного значения; `unit` тип имеет только одно значение, который выступает в качестве заполнителя, если другое значение не существует или не требуется.</span><span class="sxs-lookup"><span data-stu-id="68f92-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="68f92-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68f92-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="68f92-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="68f92-106">Remarks</span></span>

<span data-ttu-id="68f92-107">Каждое выражение F # должны иметь значение.</span><span class="sxs-lookup"><span data-stu-id="68f92-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="68f92-108">Для выражений, которые не создают значение, которое не представляет интереса, значение типа `unit` используется.</span><span class="sxs-lookup"><span data-stu-id="68f92-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="68f92-109">`unit` Тип напоминает `void` тип на языках, таких как C# и C++.</span><span class="sxs-lookup"><span data-stu-id="68f92-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="68f92-110">`unit` Тип имеет одно значение, и это значение обозначается токеном `()`.</span><span class="sxs-lookup"><span data-stu-id="68f92-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="68f92-111">Значение `unit` типа часто используются в программировании для хранения в место, где требуется значение с помощью синтаксиса языка, но в том случае, если значение не является вам F #.</span><span class="sxs-lookup"><span data-stu-id="68f92-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="68f92-112">Примером может служить возвращаемое значение `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="68f92-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="68f92-113">Поскольку важные действия `printf` выполнение операции в функции, функции не обязательно возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="68f92-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="68f92-114">Таким образом, возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="68f92-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="68f92-115">Некоторые конструкции ожидают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="68f92-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="68f92-116">Например `do` привязки или любого кода на верхнем уровне модуля является ожидаемым результатом вычисления `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="68f92-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="68f92-117">Компилятор выдает предупреждение при `do` привязкой или кодом на верхнем уровне модуля дает результат, отличное от `unit` значение, которое не используется, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68f92-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="68f92-118">Это предупреждение — это характеристика функционального программирования; он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="68f92-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="68f92-119">В чисто функциональные программы, в котором функции не имеют никаких побочных эффектов, конечное возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="68f92-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="68f92-120">Таким образом результат учитывается, при возможных ошибок программирования.</span><span class="sxs-lookup"><span data-stu-id="68f92-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="68f92-121">Несмотря на то, что F # не является чисто функциональным языком программирования, рекомендуется следовать функциональном стиле программирования, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="68f92-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="68f92-122">См. также</span><span class="sxs-lookup"><span data-stu-id="68f92-122">See also</span></span>

- [<span data-ttu-id="68f92-123">Примитив</span><span class="sxs-lookup"><span data-stu-id="68f92-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="68f92-124">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="68f92-124">F# Language Reference</span></span>](index.md)
