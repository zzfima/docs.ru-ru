---
title: Оператор | (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 374adc30e6937a68d67bfae152f2546c854b829b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1a7e9-102">Оператор | (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1a7e9-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="1a7e9-103">Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="1a7e9-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="1a7e9-104">Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="1a7e9-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="1a7e9-105">Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="1a7e9-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a7e9-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a7e9-106">Remarks</span></span>  
 <span data-ttu-id="1a7e9-107">Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="1a7e9-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a7e9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1a7e9-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1a7e9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1a7e9-109">See Also</span></span>  
 [<span data-ttu-id="1a7e9-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1a7e9-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1a7e9-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1a7e9-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1a7e9-112">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1a7e9-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
