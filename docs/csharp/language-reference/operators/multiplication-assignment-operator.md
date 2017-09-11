---
title: "Оператор *= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="f2ddf-102">Оператор *= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f2ddf-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="f2ddf-103">Бинарный оператор присваивания умножения.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ddf-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2ddf-104">Remarks</span></span>  
 <span data-ttu-id="f2ddf-105">Выражение, использующее оператор присваивания `*=`, такое как</span><span class="sxs-lookup"><span data-stu-id="f2ddf-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="f2ddf-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="f2ddf-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="f2ddf-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f2ddf-108">Для числовых типов [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) используется для выполнения операций умножения.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="f2ddf-109">Оператор `*=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) (см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="f2ddf-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2ddf-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f2ddf-110">Example</span></span>  
 <span data-ttu-id="f2ddf-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2ddf-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ddf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ddf-112">See Also</span></span>  
 <span data-ttu-id="f2ddf-113">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2ddf-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f2ddf-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2ddf-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f2ddf-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f2ddf-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

