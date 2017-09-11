---
title: "Оператор /= (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e5b61-102">Оператор /= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e5b61-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="e5b61-103">Оператор присваивания деления.</span><span class="sxs-lookup"><span data-stu-id="e5b61-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5b61-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5b61-104">Remarks</span></span>  
 <span data-ttu-id="e5b61-105">Выражение, использующее оператор присваивания `/=`, такое как</span><span class="sxs-lookup"><span data-stu-id="e5b61-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="e5b61-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="e5b61-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="e5b61-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="e5b61-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e5b61-108">В числовых типах [оператор /](../../../csharp/language-reference/operators/division-operator.md) используется для выполнения операций деления.</span><span class="sxs-lookup"><span data-stu-id="e5b61-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="e5b61-109">Оператор `/=` нельзя перегрузить напрямую, однако пользовательские типы могут перегрузить [оператор /](../../../csharp/language-reference/operators/division-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e5b61-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e5b61-110">В случае всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.</span><span class="sxs-lookup"><span data-stu-id="e5b61-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5b61-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e5b61-111">Example</span></span>  
 <span data-ttu-id="e5b61-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5b61-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b61-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e5b61-113">See Also</span></span>  
 <span data-ttu-id="e5b61-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5b61-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e5b61-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5b61-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e5b61-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="e5b61-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

