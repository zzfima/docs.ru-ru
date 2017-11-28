---
title: "Оператор &amp; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="2e854-102">Оператор &amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2e854-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="2e854-103">Оператор & может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="2e854-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e854-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e854-104">Remarks</span></span>  
 <span data-ttu-id="2e854-105">Унарный оператор & возвращает адрес своего операнда (в этом случае требуется контекст [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="2e854-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="2e854-106">Бинарные операторы & предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="2e854-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="2e854-107">Для целочисленных типов оператор & выполняет побитовую логическую операцию И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="2e854-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="2e854-108">Для операндов типа `bool` оператор & выполняет логическую операцию И для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда оба операнда имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2e854-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="2e854-109">Оператор `&` вычисляет оба оператора независимо от значения первого из них.</span><span class="sxs-lookup"><span data-stu-id="2e854-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="2e854-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="2e854-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="2e854-111">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `&` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="2e854-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="2e854-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="2e854-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="2e854-113">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="2e854-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e854-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2e854-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2e854-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2e854-115">See Also</span></span>  
 [<span data-ttu-id="2e854-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2e854-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2e854-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2e854-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2e854-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2e854-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
