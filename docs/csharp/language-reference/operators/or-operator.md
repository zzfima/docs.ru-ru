---
title: Справочник по C#. Оператор |
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333516"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4a9f4-102">Справочник по C#. Оператор |</span><span class="sxs-lookup"><span data-stu-id="4a9f4-102">| operator (C# Reference)</span></span>

<span data-ttu-id="4a9f4-103">Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="4a9f4-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="4a9f4-104">Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="4a9f4-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="4a9f4-105">Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4a9f4-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a9f4-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a9f4-106">Remarks</span></span>

<span data-ttu-id="4a9f4-107">Бинарный оператор `|` вычисляет оба операнда независимо от значения первого из них, в отличие от [условного оператора OR](conditional-or-operator.md)`||`.</span><span class="sxs-lookup"><span data-stu-id="4a9f4-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>

<span data-ttu-id="4a9f4-108">Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="4a9f4-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="4a9f4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="4a9f4-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="4a9f4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4a9f4-110">See also</span></span>

- [<span data-ttu-id="4a9f4-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4a9f4-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4a9f4-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4a9f4-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4a9f4-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="4a9f4-113">C# operators</span></span>](index.md)