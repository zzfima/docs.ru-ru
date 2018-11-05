---
title: Оператор += (справочник по C#)
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192035"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2eee6-102">Оператор += (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2eee6-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="2eee6-103">Оператор присваивания сложения.</span><span class="sxs-lookup"><span data-stu-id="2eee6-103">The addition assignment operator.</span></span>

<span data-ttu-id="2eee6-104">Выражение, использующее оператор `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="2eee6-104">An expression using the `+=` operator, such as</span></span>  

```csharp
x += y
```  

<span data-ttu-id="2eee6-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="2eee6-105">is equivalent to</span></span>  

```csharp
x = x + y
```  

<span data-ttu-id="2eee6-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="2eee6-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="2eee6-107">Для числовых типов [оператор сложения](addition-operator.md) `+` вычисляет сумму операндов.</span><span class="sxs-lookup"><span data-stu-id="2eee6-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="2eee6-108">Если один или оба операнда имеют [строковый](../keywords/string.md) тип, оператор сцепляет строковые представления операндов.</span><span class="sxs-lookup"><span data-stu-id="2eee6-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="2eee6-109">Для типов делегатов оператор `+` возвращает новый экземпляр делегата, который представляет собой комбинацию операндов.</span><span class="sxs-lookup"><span data-stu-id="2eee6-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="2eee6-110">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор сложения](addition-operator.md) `+`, оператор присваивания сложения `+=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="2eee6-110">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span>

<span data-ttu-id="2eee6-111">Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="2eee6-111">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="2eee6-112">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="2eee6-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="2eee6-113">В следующем примере иллюстрируется использование оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="2eee6-113">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a><span data-ttu-id="2eee6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2eee6-114">See also</span></span>

- [<span data-ttu-id="2eee6-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2eee6-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2eee6-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2eee6-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2eee6-117">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2eee6-117">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2eee6-118">События</span><span class="sxs-lookup"><span data-stu-id="2eee6-118">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="2eee6-119">Делегаты</span><span class="sxs-lookup"><span data-stu-id="2eee6-119">Delegates</span></span>](../../programming-guide/delegates/index.md)
