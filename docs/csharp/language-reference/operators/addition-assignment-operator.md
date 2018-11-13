---
title: Оператор += (справочник по C#)
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ac9330e283cb58ae4e0ee7b644aa2c22bdf64c46
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192035"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="eb8a9-102">Оператор += (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="eb8a9-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="eb8a9-103">Оператор присваивания сложения.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-103">The addition assignment operator.</span></span>

<span data-ttu-id="eb8a9-104">Выражение, использующее оператор `+=`, такое как</span><span class="sxs-lookup"><span data-stu-id="eb8a9-104">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="eb8a9-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="eb8a9-105">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="eb8a9-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="eb8a9-107">Для числовых типов [оператор сложения](addition-operator.md) `+` вычисляет сумму операндов.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="eb8a9-108">Если один или оба операнда имеют [строковый](../keywords/string.md) тип, оператор сцепляет строковые представления операндов.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="eb8a9-109">Для типов делегатов оператор `+` возвращает новый экземпляр делегата, который представляет собой комбинацию операндов.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="eb8a9-110">Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="eb8a9-110">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="eb8a9-111">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="eb8a9-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="eb8a9-112">В следующем примере иллюстрируется использование оператора `+=`.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-112">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="eb8a9-113">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="eb8a9-113">Operator overloadability</span></span>

<span data-ttu-id="eb8a9-114">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор сложения](addition-operator.md) `+`, оператор присваивания сложения `+=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-114">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span> <span data-ttu-id="eb8a9-115">Определяемый пользователем тип не может перегружать оператор присваивания сложения явным образом.</span><span class="sxs-lookup"><span data-stu-id="eb8a9-115">A user-defined type cannot explicitly overload the addition assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eb8a9-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="eb8a9-116">C# language specification</span></span>

<span data-ttu-id="eb8a9-117">Дополнительные сведения см. в разделах [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) и [Назначение событий](~/_csharplang/spec/expressions.md#event-assignment) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb8a9-117">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) and [Event assignment](~/_csharplang/spec/expressions.md#event-assignment) sections of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb8a9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="eb8a9-118">See also</span></span>

- [<span data-ttu-id="eb8a9-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="eb8a9-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eb8a9-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eb8a9-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eb8a9-121">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="eb8a9-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="eb8a9-122">События</span><span class="sxs-lookup"><span data-stu-id="eb8a9-122">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="eb8a9-123">Делегаты</span><span class="sxs-lookup"><span data-stu-id="eb8a9-123">Delegates</span></span>](../../programming-guide/delegates/index.md)
