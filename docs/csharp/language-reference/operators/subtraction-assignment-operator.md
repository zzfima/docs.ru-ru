---
title: Справочник по C#. Оператор -=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333334"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="7c3e3-102">Справочник по C#. Оператор -=</span><span class="sxs-lookup"><span data-stu-id="7c3e3-102">-= operator (C# Reference)</span></span>

<span data-ttu-id="7c3e3-103">Оператор присваивания вычитания.</span><span class="sxs-lookup"><span data-stu-id="7c3e3-103">The subtraction assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c3e3-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c3e3-104">Remarks</span></span>

<span data-ttu-id="7c3e3-105">Выражение, использующее оператор присваивания `-=`, такое как</span><span class="sxs-lookup"><span data-stu-id="7c3e3-105">An expression using the `-=` assignment operator, such as</span></span>

```csharp
x -= y
```

 <span data-ttu-id="7c3e3-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="7c3e3-106">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="7c3e3-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="7c3e3-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="7c3e3-108">Значение [- operator](subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="7c3e3-108">The meaning of the [- operator](subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>

<span data-ttu-id="7c3e3-109">Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](subtraction-operator.md) (см. [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7c3e3-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](subtraction-operator.md) (see [operator](../keywords/operator.md)).</span></span>

<span data-ttu-id="7c3e3-110">Оператор -= также используется в C# для отмены подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="7c3e3-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="7c3e3-111">Дополнительные сведения см. в разделе [Как подписке и отмене подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="7c3e3-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c3e3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7c3e3-112">Example</span></span>

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a><span data-ttu-id="7c3e3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7c3e3-113">See also</span></span>

- [<span data-ttu-id="7c3e3-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7c3e3-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7c3e3-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7c3e3-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7c3e3-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="7c3e3-116">C# operators</span></span>](index.md)
