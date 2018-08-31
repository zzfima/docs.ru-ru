---
title: Оператор | (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001234"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ee10c-102">Оператор | (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ee10c-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="ee10c-103">Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="ee10c-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="ee10c-104">Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="ee10c-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="ee10c-105">Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ee10c-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee10c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee10c-106">Remarks</span></span>  
 <span data-ttu-id="ee10c-107">Бинарный оператор `|` вычисляет оба оператора независимо от значения первого из них, в отличие от [условного оператора ИЛИ]     (conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="ee10c-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator]     (conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="ee10c-108">Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="ee10c-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee10c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ee10c-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ee10c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ee10c-110">See Also</span></span>

- [<span data-ttu-id="ee10c-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ee10c-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ee10c-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ee10c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ee10c-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ee10c-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
