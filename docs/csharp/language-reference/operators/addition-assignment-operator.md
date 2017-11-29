---
title: "Оператор += (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 91286b3c6b9a7239bcd5d5bac0ef08bfd7fa8345
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bf015-102">Оператор += (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bf015-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="bf015-103">Оператор присваивания сложения.</span><span class="sxs-lookup"><span data-stu-id="bf015-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf015-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf015-104">Remarks</span></span>  
 <span data-ttu-id="bf015-105">Выражение, использующее оператор присваивания `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="bf015-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="bf015-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="bf015-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="bf015-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="bf015-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="bf015-108">Значение [оператора +](../../../csharp/language-reference/operators/addition-operator.md) зависит от типов операндов `x` и `y` (сложение для числовых операндов, объединение для строковых операндов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="bf015-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="bf015-109">Оператор `+=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор +](../../../csharp/language-reference/operators/addition-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bf015-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="bf015-110">Оператор `+=` также позволяет указать метод, который будет вызываться в ответ на событие. Такие методы называются обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="bf015-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="bf015-111">Использование оператора `+=` в таком контексте называется *подпиской на событие*.</span><span class="sxs-lookup"><span data-stu-id="bf015-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="bf015-112">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="bf015-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="bf015-113">и [Делегаты](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf015-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf015-114">Пример</span><span class="sxs-lookup"><span data-stu-id="bf015-114">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bf015-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bf015-115">See Also</span></span>  
 [<span data-ttu-id="bf015-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bf015-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bf015-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bf015-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bf015-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="bf015-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
