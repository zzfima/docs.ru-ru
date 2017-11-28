---
title: "Оператор % (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5eb24-102">Оператор % (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5eb24-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="5eb24-103">Оператор `%` вычисляет остаток от деления первого операнда на второй.</span><span class="sxs-lookup"><span data-stu-id="5eb24-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="5eb24-104">Все числовые типы имеют предопределенные операторы вычисления остатка.</span><span class="sxs-lookup"><span data-stu-id="5eb24-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5eb24-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5eb24-105">Remarks</span></span>  
 <span data-ttu-id="5eb24-106">Определяемые пользователем типы могут вызвать перегрузку оператора `%` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="5eb24-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="5eb24-107">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="5eb24-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb24-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5eb24-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="5eb24-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5eb24-109">Comments</span></span>  
 <span data-ttu-id="5eb24-110">Обратите внимание на ошибки округления, связанные с использованием типа double.</span><span class="sxs-lookup"><span data-stu-id="5eb24-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb24-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5eb24-111">See Also</span></span>  
 [<span data-ttu-id="5eb24-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5eb24-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5eb24-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5eb24-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5eb24-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="5eb24-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
