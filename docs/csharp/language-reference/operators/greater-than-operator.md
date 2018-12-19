---
title: Оператор &gt;. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 13ec8aa8a98984bc43a349369dd16364edf5cbf3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239596"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="01ea8-102">Оператор &gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="01ea8-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="01ea8-103">Все числовые типы и типы перечисления определяют оператор отношения "больше" (`>`), который возвращает `true`, если первый операнд больше второго. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="01ea8-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01ea8-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="01ea8-104">Remarks</span></span>  
 <span data-ttu-id="01ea8-105">Определяемые пользователем типы могут вызвать перегрузку оператора `>` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="01ea8-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="01ea8-106">В случае перегрузки `>` также необходимо перегружать [<](../../../csharp/language-reference/operators/less-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="01ea8-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="01ea8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="01ea8-107">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="01ea8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="01ea8-108">See Also</span></span>

- [<span data-ttu-id="01ea8-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="01ea8-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="01ea8-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="01ea8-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="01ea8-111">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="01ea8-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="01ea8-112">explicit</span><span class="sxs-lookup"><span data-stu-id="01ea8-112">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
