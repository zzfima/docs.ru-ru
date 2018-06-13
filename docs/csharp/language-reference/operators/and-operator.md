---
title: Оператор &amp; (справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267884"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="86caf-102">Оператор &amp; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="86caf-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="86caf-103">Оператор `&` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="86caf-103">The `&` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86caf-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="86caf-104">Remarks</span></span>  
 <span data-ttu-id="86caf-105">Унарный оператор `&` возвращает адрес своего операнда (в этом случае требуется контекст [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).</span><span class="sxs-lookup"><span data-stu-id="86caf-105">The unary `&` operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="86caf-106">Бинарные операторы `&` предварительно определены для целочисленных типов и типа `bool`.</span><span class="sxs-lookup"><span data-stu-id="86caf-106">Binary `&` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="86caf-107">Для целочисленных типов оператор & выполняет побитовую логическую операцию И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="86caf-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="86caf-108">Для операндов типа `bool` оператор & выполняет логическую операцию И для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда оба операнда имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="86caf-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="86caf-109">Бинарный оператор `&` вычисляет оба оператора независимо от значения первого из них, в отличие от [условного оператора AND](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span><span class="sxs-lookup"><span data-stu-id="86caf-109">The binary `&` operator evaluates both operators regardless of the first one's value, in contrast to the [conditional AND operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span></span> <span data-ttu-id="86caf-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="86caf-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="86caf-111">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `&` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="86caf-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="86caf-112">Операции с целыми типами обычно разрешены и для перечислений.</span><span class="sxs-lookup"><span data-stu-id="86caf-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="86caf-113">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="86caf-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86caf-114">Пример</span><span class="sxs-lookup"><span data-stu-id="86caf-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="86caf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="86caf-115">See Also</span></span>  
 [<span data-ttu-id="86caf-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="86caf-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="86caf-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="86caf-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="86caf-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="86caf-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
