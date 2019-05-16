---
title: Тип Unit
description: Узнайте, как F# тип «unit» часто используется для хранения в место, где требуется значение с помощью синтаксиса языка Если значение не является вам.
ms.date: 05/16/2016
ms.openlocfilehash: d515e19489bfa7de6f17194fd74176cfa0bcd7c9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645126"
---
# <a name="unit-type"></a><span data-ttu-id="c7ec5-103">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="c7ec5-103">Unit Type</span></span>

<span data-ttu-id="c7ec5-104">`unit` Тип является типом, который указывает на отсутствие конкретного значения; `unit` тип имеет только одно значение, который выступает в качестве заполнителя, если другое значение не существует или не требуется.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7ec5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7ec5-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="c7ec5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7ec5-106">Remarks</span></span>

<span data-ttu-id="c7ec5-107">Каждый F# выражение должно возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="c7ec5-108">Для выражений, которые не создают значение, которое не представляет интереса, значение типа `unit` используется.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="c7ec5-109">`unit` Тип напоминает `void` тип на языках, таких как C# и C++.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="c7ec5-110">`unit` Тип имеет одно значение, и это значение обозначается токеном `()`.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="c7ec5-111">Значение `unit` типа часто используются в F# программирования для хранения в место, где требуется значение с помощью синтаксиса языка, но в том случае, если значение не является вам.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="c7ec5-112">Примером может служить возвращаемое значение `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="c7ec5-113">Поскольку важные действия `printf` выполнение операции в функции, функции не обязательно возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="c7ec5-114">Таким образом, возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="c7ec5-115">Некоторые конструкции ожидают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="c7ec5-116">Например `do` привязки или любого кода на верхнем уровне модуля является ожидаемым результатом вычисления `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="c7ec5-117">Компилятор выдает предупреждение при `do` привязкой или кодом на верхнем уровне модуля дает результат, отличное от `unit` значение, которое не используется, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="c7ec5-118">Это предупреждение — это характеристика функционального программирования; он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="c7ec5-119">В чисто функциональные программы, в котором функции не имеют никаких побочных эффектов, конечное возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="c7ec5-120">Таким образом результат учитывается, при возможных ошибок программирования.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="c7ec5-121">Несмотря на то что F# не является чисто функциональным языка программирования, рекомендуется следовать функциональном стиле программирования, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="c7ec5-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ec5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c7ec5-122">See also</span></span>

- [<span data-ttu-id="c7ec5-123">Примитив</span><span class="sxs-lookup"><span data-stu-id="c7ec5-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="c7ec5-124">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c7ec5-124">F# Language Reference</span></span>](index.md)
