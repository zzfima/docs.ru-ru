---
title: Справочник по C#. Оператор |=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333269"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2d6e9-102">Справочник по C#. Оператор |=</span><span class="sxs-lookup"><span data-stu-id="2d6e9-102">|= operator (C# Reference)</span></span>

<span data-ttu-id="2d6e9-103">Оператор присваивания ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-103">The OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d6e9-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d6e9-104">Remarks</span></span>

<span data-ttu-id="2d6e9-105">Выражение, использующее оператор присваивания `|=`, такое как</span><span class="sxs-lookup"><span data-stu-id="2d6e9-105">An expression using the `|=` assignment operator, such as</span></span>

```csharp
x |= y
```

<span data-ttu-id="2d6e9-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="2d6e9-106">is equivalent to</span></span>

```csharp
x = x | y
```

<span data-ttu-id="2d6e9-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="2d6e9-108">[Оператор &#124;](or-operator.md) выполняет побитовую операцию ИЛИ в отношении целочисленных операндов и логическую операцию ИЛИ в отношении операндов типа bool.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-108">The [&#124; operator](or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>

<span data-ttu-id="2d6e9-109">Оператор `|=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор &#124;](or-operator.md) (см. [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="2d6e9-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](or-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="2d6e9-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2d6e9-110">Example</span></span>

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a><span data-ttu-id="2d6e9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2d6e9-111">See also</span></span>

- [<span data-ttu-id="2d6e9-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2d6e9-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2d6e9-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2d6e9-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2d6e9-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2d6e9-114">C# operators</span></span>](index.md)