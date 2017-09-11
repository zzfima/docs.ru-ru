---
title: "Оператор += (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
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
ms.openlocfilehash: 42567b2d8e7d9b694ce64ccb88e0fd4bfe05b020
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="d341f-102">Оператор += (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d341f-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="d341f-103">Оператор присваивания сложения.</span><span class="sxs-lookup"><span data-stu-id="d341f-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d341f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d341f-104">Remarks</span></span>  
 <span data-ttu-id="d341f-105">Выражение, использующее оператор присваивания `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="d341f-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="d341f-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="d341f-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="d341f-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="d341f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d341f-108">Значение [оператора +](../../../csharp/language-reference/operators/addition-operator.md) зависит от типов операндов `x` и `y` (сложение для числовых операндов, объединение для строковых операндов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="d341f-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="d341f-109">Оператор `+=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор +](../../../csharp/language-reference/operators/addition-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="d341f-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="d341f-110">Оператор `+=` также позволяет указать метод, который будет вызываться в ответ на событие. Такие методы называются обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="d341f-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="d341f-111">Использование оператора `+=` в таком контексте называется *подпиской на событие*.</span><span class="sxs-lookup"><span data-stu-id="d341f-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="d341f-112">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="d341f-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="d341f-113">и [Делегаты](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="d341f-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d341f-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d341f-114">Example</span></span>  
 <span data-ttu-id="d341f-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d341f-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d341f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d341f-116">See Also</span></span>  
 <span data-ttu-id="d341f-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d341f-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d341f-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d341f-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="d341f-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="d341f-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

