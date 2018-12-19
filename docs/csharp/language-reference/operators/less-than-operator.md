---
title: Оператор &lt;. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: 3cc125471eee7bf0002e9844c2a1cdc05e8d4a03
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241240"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="e7ead-102">Оператор &lt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e7ead-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="e7ead-103">Все числовые типы и типы перечисления определяют оператор отношения "меньше" (`<`), который возвращает `true`, если первый операнд меньше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="e7ead-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7ead-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7ead-104">Remarks</span></span>  
 <span data-ttu-id="e7ead-105">Определяемые пользователем типы могут вызвать перегрузку оператора `<` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="e7ead-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e7ead-106">В случае перегрузки `<` также необходимо перегружать [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e7ead-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="e7ead-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e7ead-107">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e7ead-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e7ead-108">See Also</span></span>

- [<span data-ttu-id="e7ead-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e7ead-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e7ead-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e7ead-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e7ead-111">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e7ead-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
