---
title: "Оператор == (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3e50d-102">Оператор == (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3e50d-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="3e50d-103">Для предопределенных типов значений оператор равенства (`==`) возвращает значение true, если значения его операндов равны, и `false` в любых остальных случаях.</span><span class="sxs-lookup"><span data-stu-id="3e50d-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="3e50d-104">Для ссылочных типов (кроме [string](../../../csharp/language-reference/keywords/string.md)) оператор `==` возвращает `true`, если оба его операнда ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="3e50d-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="3e50d-105">Для типа `string` оператор `==` сравнивает значения строк.</span><span class="sxs-lookup"><span data-stu-id="3e50d-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e50d-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e50d-106">Remarks</span></span>  
 <span data-ttu-id="3e50d-107">Определяемые пользователем типы значений могут вызвать перегрузку оператора `==` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3e50d-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3e50d-108">Это справедливо и для определяемых пользователем ссылочных типов, хотя оператор `==` по умолчанию действует описанным выше способом и для предопределенных, и для определяемых пользователем ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="3e50d-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="3e50d-109">В случае перегрузки `==` также необходимо перегружать [!=](../../../csharp/language-reference/operators/not-equal-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3e50d-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="3e50d-110">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="3e50d-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e50d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3e50d-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3e50d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3e50d-112">See Also</span></span>  
 [<span data-ttu-id="3e50d-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3e50d-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3e50d-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3e50d-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3e50d-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="3e50d-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
