---
title: "Оператор |= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
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
ms.openlocfilehash: f1c0a92414739efc2ab091871e80852737fdf931
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="d4776-102">Оператор |= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d4776-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="d4776-103">Оператор присваивания ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="d4776-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4776-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4776-104">Remarks</span></span>  
 <span data-ttu-id="d4776-105">Выражение, использующее оператор присваивания `|=`, такое как</span><span class="sxs-lookup"><span data-stu-id="d4776-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="d4776-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="d4776-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="d4776-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="d4776-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d4776-108">[Оператор &#124;](../../../csharp/language-reference/operators/or-operator.md) выполняет побитовую операцию ИЛИ в отношении целочисленных операндов и логическую операцию ИЛИ в отношении операндов типа bool.</span><span class="sxs-lookup"><span data-stu-id="d4776-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="d4776-109">Оператор `|=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор &#124;](../../../csharp/language-reference/operators/or-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="d4776-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4776-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d4776-110">Example</span></span>  
 <span data-ttu-id="d4776-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d4776-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4776-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d4776-112">See Also</span></span>  
 <span data-ttu-id="d4776-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4776-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d4776-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4776-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="d4776-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d4776-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

