---
title: Тип Unit
description: Узнайте, как F# тип "единица" часто используется для хранения места, где значение является обязательным для синтаксиса языка, когда значение не требуется или нужно.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424032"
---
# <a name="unit-type"></a><span data-ttu-id="121b6-103">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="121b6-103">Unit Type</span></span>

<span data-ttu-id="121b6-104">Тип `unit` — это тип, который указывает на отсутствие определенного значения; Тип `unit` имеет только одно значение, которое выступает в качестве заполнителя, если другие значения не существуют или не требуются.</span><span class="sxs-lookup"><span data-stu-id="121b6-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="121b6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="121b6-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="121b6-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="121b6-106">Remarks</span></span>

<span data-ttu-id="121b6-107">Каждое F# выражение должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="121b6-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="121b6-108">Для выражений, которые не создают значение, представляющее интерес, используется значение типа `unit`.</span><span class="sxs-lookup"><span data-stu-id="121b6-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="121b6-109">Тип `unit` похож на тип `void` в таких языках, как C# и. C++</span><span class="sxs-lookup"><span data-stu-id="121b6-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="121b6-110">Тип `unit` имеет одно значение, и это значение обозначается токеном `()`.</span><span class="sxs-lookup"><span data-stu-id="121b6-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="121b6-111">Значение типа `unit` часто используется в F# программировании для хранения места, где значение является обязательным для синтаксиса языка, но если значение не требуется или необходимо.</span><span class="sxs-lookup"><span data-stu-id="121b6-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="121b6-112">Примером может быть возвращаемое значение функции `printf`.</span><span class="sxs-lookup"><span data-stu-id="121b6-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="121b6-113">Поскольку важные действия `printf` операции выполняются в функции, функция не должна возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="121b6-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="121b6-114">Поэтому возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="121b6-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="121b6-115">Некоторые конструкции предполагают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="121b6-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="121b6-116">Например, ожидается, что для привязки `do` или любого кода на верхнем уровне модуля вычисляется значение `unit`.</span><span class="sxs-lookup"><span data-stu-id="121b6-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="121b6-117">Компилятор сообщает о предупреждении, когда `do` привязка или код на верхнем уровне модуля выдает результат, отличный от неиспользуемого `unit`ого значения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="121b6-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="121b6-118">Это предупреждение является характеристикой функционального программирования. Он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="121b6-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="121b6-119">В чисто функциональной программе, в которой функции не имеют побочных эффектов, Последнее возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="121b6-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="121b6-120">Поэтому при игнорировании результата возможной ошибкой программирования.</span><span class="sxs-lookup"><span data-stu-id="121b6-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="121b6-121">Несмотря F# на то, что не является чисто функциональным языком программирования, рекомендуется всегда следовать стилю функционального программирования, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="121b6-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="121b6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="121b6-122">See also</span></span>

- [<span data-ttu-id="121b6-123">Простого</span><span class="sxs-lookup"><span data-stu-id="121b6-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="121b6-124">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="121b6-124">F# Language Reference</span></span>](index.md)
