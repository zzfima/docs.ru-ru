---
title: Оператор += (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bd0997ec5b7d79a41e01f9c2b17533293e412c1e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468413"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b2c0a-102">Оператор += (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b2c0a-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="b2c0a-103">Оператор присваивания сложения.</span><span class="sxs-lookup"><span data-stu-id="b2c0a-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2c0a-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2c0a-104">Remarks</span></span>  
 <span data-ttu-id="b2c0a-105">Выражение, использующее оператор присваивания `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="b2c0a-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```csharp  
x += y  
```  
  
 <span data-ttu-id="b2c0a-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="b2c0a-106">is equivalent to</span></span>  
  
```csharp  
x = x + y  
```  
  
 <span data-ttu-id="b2c0a-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b2c0a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b2c0a-108">Значение [оператора +](../../../csharp/language-reference/operators/addition-operator.md) зависит от типов операндов `x` и `y` (сложение для числовых операндов, объединение для строковых операндов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="b2c0a-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="b2c0a-109">Оператор `+=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор +](../../../csharp/language-reference/operators/addition-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b2c0a-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="b2c0a-110">Оператор `+=` также позволяет указать метод, который будет вызываться в ответ на событие. Такие методы называются обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="b2c0a-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="b2c0a-111">Использование оператора `+=` в таком контексте называется *подпиской на событие*.</span><span class="sxs-lookup"><span data-stu-id="b2c0a-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="b2c0a-112">Дополнительные сведения см. в разделах [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) и [Делегаты](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2c0a-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2c0a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b2c0a-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b2c0a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b2c0a-114">See Also</span></span>

- [<span data-ttu-id="b2c0a-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b2c0a-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b2c0a-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b2c0a-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b2c0a-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b2c0a-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
