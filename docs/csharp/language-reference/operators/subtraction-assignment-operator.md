---
title: Справочник по C#. Оператор -=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: dc3cedafc57e1c6ec9bc34ca4e2c2aa9c604848c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239589"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="b7ba7-102">Оператор -= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b7ba7-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="b7ba7-103">Оператор присваивания вычитания.</span><span class="sxs-lookup"><span data-stu-id="b7ba7-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7ba7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7ba7-104">Remarks</span></span>  
 <span data-ttu-id="b7ba7-105">Выражение, использующее оператор присваивания `-=`, такое как</span><span class="sxs-lookup"><span data-stu-id="b7ba7-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="b7ba7-106">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="b7ba7-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="b7ba7-107">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b7ba7-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b7ba7-108">Значение [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).</span><span class="sxs-lookup"><span data-stu-id="b7ba7-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="b7ba7-109">Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b7ba7-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="b7ba7-110">Оператор -= также используется в C# для отмены подписки на событие.</span><span class="sxs-lookup"><span data-stu-id="b7ba7-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="b7ba7-111">Дополнительные сведения см. в разделе [Как подписке и отмене подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="b7ba7-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7ba7-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b7ba7-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b7ba7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b7ba7-113">See Also</span></span>

- [<span data-ttu-id="b7ba7-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b7ba7-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b7ba7-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b7ba7-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b7ba7-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b7ba7-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
