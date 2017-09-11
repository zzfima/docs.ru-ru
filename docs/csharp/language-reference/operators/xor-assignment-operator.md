---
title: "Оператор ^= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e636e-102">Оператор ^= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e636e-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="e636e-103">Оператор присваивания исключающего ИЛИ.</span><span class="sxs-lookup"><span data-stu-id="e636e-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e636e-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e636e-104">Remarks</span></span>  
 <span data-ttu-id="e636e-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="e636e-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="e636e-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="e636e-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="e636e-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="e636e-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e636e-108">[Оператор ^](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="e636e-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="e636e-109">Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e636e-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e636e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e636e-110">Example</span></span>  
 <span data-ttu-id="e636e-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e636e-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e636e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e636e-112">See Also</span></span>  
 <span data-ttu-id="e636e-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e636e-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e636e-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e636e-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e636e-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e636e-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

