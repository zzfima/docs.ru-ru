---
title: Оператор % (Справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271079"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b53b3-102">Оператор % (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b53b3-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="b53b3-103">Оператор остатка (`%`) вычисляет остаток от деления первого операнда на второй.</span><span class="sxs-lookup"><span data-stu-id="b53b3-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="b53b3-104">Все числовые типы имеют предопределенные операторы вычисления остатка.</span><span class="sxs-lookup"><span data-stu-id="b53b3-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b53b3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b53b3-105">Remarks</span></span>  
 <span data-ttu-id="b53b3-106">Формула `a % b` всегда возвращает значение в диапазоне `(-b, b)`, исключая границы (она не может вернуть значение `b` или `-b`), с сохранением знака делимого.</span><span class="sxs-lookup"><span data-stu-id="b53b3-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="b53b3-107">При целочисленном делении для оператора остатка соблюдается правило `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="b53b3-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="b53b3-108">Эту операцию не следует путать с получением канонического модуля, которое следует тому же правилу, но округление производится к меньшему и возвращаются значения в диапазоне `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="b53b3-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="b53b3-109">В C# нет оператора для получения канонического модуля.</span><span class="sxs-lookup"><span data-stu-id="b53b3-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="b53b3-110">Однако для положительного делимого результат будет аналогичным.</span><span class="sxs-lookup"><span data-stu-id="b53b3-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="b53b3-111">Определяемые пользователем типы могут вызвать перегрузку оператора `%` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="b53b3-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b53b3-112">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="b53b3-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b53b3-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b53b3-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="b53b3-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b53b3-114">Comments</span></span>  
 <span data-ttu-id="b53b3-115">Обратите внимание на ошибки округления, связанные с использованием типа double.</span><span class="sxs-lookup"><span data-stu-id="b53b3-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53b3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b53b3-116">See Also</span></span>  
 [<span data-ttu-id="b53b3-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b53b3-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b53b3-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b53b3-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b53b3-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b53b3-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
