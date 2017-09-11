---
title: "Оператор &lt;&lt;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
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
ms.openlocfilehash: fd562a538891a5592cc724e74cffb3d086248898
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="30374-102">Оператор &lt;&lt;= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="30374-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="30374-103">Оператор присваивания сдвига влево.</span><span class="sxs-lookup"><span data-stu-id="30374-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30374-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="30374-104">Remarks</span></span>  
 <span data-ttu-id="30374-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="30374-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="30374-106">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="30374-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="30374-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="30374-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="30374-108">[Оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) сдвигает `x` влево на число битов, заданное в `y`.</span><span class="sxs-lookup"><span data-stu-id="30374-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="30374-109">Оператор `<<=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор <<](../../../csharp/language-reference/operators/left-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="30374-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30374-110">Пример</span><span class="sxs-lookup"><span data-stu-id="30374-110">Example</span></span>  
 <span data-ttu-id="30374-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="30374-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30374-112">См. также</span><span class="sxs-lookup"><span data-stu-id="30374-112">See Also</span></span>  
 <span data-ttu-id="30374-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="30374-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="30374-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="30374-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="30374-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="30374-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

