---
title: "Оператор &gt;&gt;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="b730c-102">Оператор &gt;&gt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b730c-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="b730c-103">Оператор присваивания сдвига вправо.</span><span class="sxs-lookup"><span data-stu-id="b730c-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b730c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b730c-104">Remarks</span></span>  
 <span data-ttu-id="b730c-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="b730c-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="b730c-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="b730c-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="b730c-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b730c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b730c-108">[Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.</span><span class="sxs-lookup"><span data-stu-id="b730c-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="b730c-109">Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b730c-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b730c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b730c-110">Example</span></span>  
 <span data-ttu-id="b730c-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b730c-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b730c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b730c-112">See Also</span></span>  
 <span data-ttu-id="b730c-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b730c-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b730c-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b730c-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b730c-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b730c-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

