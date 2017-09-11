---
title: "Оператор &amp; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="3eb6b-102">Оператор &amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3eb6b-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="3eb6b-103">Оператор & может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb6b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eb6b-104">Remarks</span></span>  
 <span data-ttu-id="3eb6b-105">Унарный оператор & возвращает адрес своего операнда (в этом случае требуется контекст [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="3eb6b-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="3eb6b-106">Бинарные операторы & предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="3eb6b-107">Для целочисленных типов оператор & выполняет побитовую логическую операцию И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="3eb6b-108">Для операндов типа `bool` оператор & выполняет логическую операцию И для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда оба операнда имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="3eb6b-109">Оператор `&` вычисляет оба оператора независимо от значения первого из них.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="3eb6b-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="3eb6b-110">For example:</span></span>  
  
 <span data-ttu-id="3eb6b-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3eb6b-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="3eb6b-112">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `&` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="3eb6b-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3eb6b-113">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="3eb6b-114">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="3eb6b-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eb6b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="3eb6b-115">Example</span></span>  
 <span data-ttu-id="3eb6b-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3eb6b-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb6b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb6b-117">See Also</span></span>  
 <span data-ttu-id="3eb6b-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3eb6b-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3eb6b-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3eb6b-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3eb6b-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="3eb6b-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

