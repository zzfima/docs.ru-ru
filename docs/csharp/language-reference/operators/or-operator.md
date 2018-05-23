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
ms.openlocfilehash: 7b62af53f0d8b7cba29f4496887717f1726eabf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0015f-102">Оператор | (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0015f-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="0015f-103">Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="0015f-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="0015f-104">Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="0015f-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="0015f-105">Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0015f-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0015f-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="0015f-106">Remarks</span></span>  
 <span data-ttu-id="0015f-107">Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="0015f-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0015f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0015f-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0015f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0015f-109">See Also</span></span>  
 [<span data-ttu-id="0015f-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0015f-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0015f-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0015f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0015f-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0015f-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
