---
title: Оператор % (Справочник по C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0feda-102">Оператор % (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0feda-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="0feda-103">Оператор остатка (`%`) вычисляет остаток от деления первого операнда на второй.</span><span class="sxs-lookup"><span data-stu-id="0feda-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="0feda-104">Все числовые типы имеют предопределенные операторы вычисления остатка.</span><span class="sxs-lookup"><span data-stu-id="0feda-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0feda-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0feda-105">Remarks</span></span>  
 <span data-ttu-id="0feda-106">Формула `a % b` всегда возвращает значение в диапазоне `(-b, b)`, исключая границы (она не может вернуть значение `b` или `-b`), с сохранением знака делимого.</span><span class="sxs-lookup"><span data-stu-id="0feda-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="0feda-107">При целочисленном делении для оператора остатка соблюдается правило `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="0feda-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="0feda-108">Эту операцию не следует путать с получением канонического модуля, которое следует тому же правилу, но округление производится к меньшему и возвращаются значения в диапазоне `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="0feda-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="0feda-109">В C# нет оператора для получения канонического модуля.</span><span class="sxs-lookup"><span data-stu-id="0feda-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="0feda-110">Однако для положительного делимого результат будет аналогичным.</span><span class="sxs-lookup"><span data-stu-id="0feda-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="0feda-111">Определяемые пользователем типы могут вызвать перегрузку оператора `%` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="0feda-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="0feda-112">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="0feda-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0feda-113">Пример</span><span class="sxs-lookup"><span data-stu-id="0feda-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="0feda-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0feda-114">Comments</span></span>  
 <span data-ttu-id="0feda-115">Обратите внимание на ошибки округления, связанные с использованием типа double.</span><span class="sxs-lookup"><span data-stu-id="0feda-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0feda-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0feda-116">See Also</span></span>  
 [<span data-ttu-id="0feda-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0feda-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0feda-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0feda-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0feda-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0feda-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
