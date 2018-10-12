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
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46706152"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="67a32-102">Оператор | (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="67a32-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="67a32-103">Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="67a32-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="67a32-104">Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="67a32-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="67a32-105">Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="67a32-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67a32-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="67a32-106">Remarks</span></span>  
 <span data-ttu-id="67a32-107">Бинарный оператор `|` вычисляет оба операнда независимо от значения первого из них, в отличие от [условного оператора OR](conditional-or-operator.md)`||`.</span><span class="sxs-lookup"><span data-stu-id="67a32-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="67a32-108">Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="67a32-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a32-109">Пример</span><span class="sxs-lookup"><span data-stu-id="67a32-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="67a32-110">См. также</span><span class="sxs-lookup"><span data-stu-id="67a32-110">See Also</span></span>

- [<span data-ttu-id="67a32-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="67a32-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="67a32-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="67a32-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="67a32-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="67a32-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
