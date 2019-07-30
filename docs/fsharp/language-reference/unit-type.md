---
title: Тип Unit
description: Узнайте, как F# тип "единица" часто используется для хранения места, где значение является обязательным для синтаксиса языка, когда значение не требуется или нужно.
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630173"
---
# <a name="unit-type"></a><span data-ttu-id="51247-103">Тип Unit</span><span class="sxs-lookup"><span data-stu-id="51247-103">Unit Type</span></span>

<span data-ttu-id="51247-104">Тип является типом, указывающим на отсутствие определенного значения `unit` ; тип имеет только одно значение, которое выступает в качестве заполнителя, если другие значения не существуют или не требуются. `unit`</span><span class="sxs-lookup"><span data-stu-id="51247-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="51247-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51247-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="51247-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="51247-106">Remarks</span></span>

<span data-ttu-id="51247-107">Каждое F# выражение должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="51247-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="51247-108">Для выражений, которые не создают значение, представляющее интерес, используется значение типа `unit` .</span><span class="sxs-lookup"><span data-stu-id="51247-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="51247-109">Тип напоминает C# тип в таких языках, как и C++ `unit` `void`</span><span class="sxs-lookup"><span data-stu-id="51247-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="51247-110">Тип имеет одно значение, и это значение обозначается токеном `()`. `unit`</span><span class="sxs-lookup"><span data-stu-id="51247-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="51247-111">Значение `unit` типа часто используется в F# программировании для хранения места, где значение является обязательным для синтаксиса языка, но если значение не требуется или нужно.</span><span class="sxs-lookup"><span data-stu-id="51247-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="51247-112">Примером может быть возвращаемое значение `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="51247-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="51247-113">Поскольку важные действия `printf` операции выполняются в функции, функция не должна возвращать фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="51247-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="51247-114">Поэтому возвращаемое значение имеет тип `unit`.</span><span class="sxs-lookup"><span data-stu-id="51247-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="51247-115">Некоторые конструкции предполагают `unit` значение.</span><span class="sxs-lookup"><span data-stu-id="51247-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="51247-116">Например, `do` для привязки или любого кода на верхнем уровне модуля должно быть `unit` задано значение.</span><span class="sxs-lookup"><span data-stu-id="51247-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="51247-117">Компилятор сообщает о предупреждении, когда `do` привязка или код на верхнем уровне модуля выдает результат, отличный `unit` от неиспользуемого значения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="51247-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="51247-118">Это предупреждение является характеристикой функционального программирования. Он не отображается в других языках программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="51247-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="51247-119">В чисто функциональной программе, в которой функции не имеют побочных эффектов, Последнее возвращаемое значение является единственным результатом вызова функции.</span><span class="sxs-lookup"><span data-stu-id="51247-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="51247-120">Поэтому при игнорировании результата возможной ошибкой программирования.</span><span class="sxs-lookup"><span data-stu-id="51247-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="51247-121">Несмотря F# на то, что не является чисто функциональным языком программирования, рекомендуется всегда следовать стилю функционального программирования, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="51247-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="51247-122">См. также</span><span class="sxs-lookup"><span data-stu-id="51247-122">See also</span></span>

- [<span data-ttu-id="51247-123">Простого</span><span class="sxs-lookup"><span data-stu-id="51247-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="51247-124">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="51247-124">F# Language Reference</span></span>](index.md)
