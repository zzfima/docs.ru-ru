---
title: Справочник по C#. Оператор &gt;&gt;=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333697"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="ee754-102">Справочник по C#. Оператор &gt;&gt;=</span><span class="sxs-lookup"><span data-stu-id="ee754-102">&gt;&gt;= operator (C# Reference)</span></span>

<span data-ttu-id="ee754-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="ee754-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee754-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee754-104">Remarks</span></span>

<span data-ttu-id="ee754-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="ee754-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="ee754-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="ee754-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="ee754-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="ee754-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ee754-108">[Оператор >>](right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.</span><span class="sxs-lookup"><span data-stu-id="ee754-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="ee754-109">Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](right-shift-operator.md) (см. [оператор](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ee754-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="ee754-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ee754-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="ee754-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ee754-111">See also</span></span>

- [<span data-ttu-id="ee754-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ee754-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ee754-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ee754-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ee754-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ee754-114">C# operators</span></span>](index.md)