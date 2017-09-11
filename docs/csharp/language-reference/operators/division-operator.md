---
title: "Оператор / (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="7cbc3-102">Оператор / (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7cbc3-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="7cbc3-103">Оператор деления (`/`) делит первый операнд на второй.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="7cbc3-104">Все числовые типы имеют предопределенные операторы деления.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cbc3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7cbc3-105">Remarks</span></span>  
 <span data-ttu-id="7cbc3-106">Определяемые пользователем типы могут вызвать перегрузку оператора `/` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="7cbc3-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7cbc3-107">Перегрузка оператора `/` неявно перегружает [ оператор /= ](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7cbc3-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="7cbc3-108">При делении двух целых чисел результат всегда является целочисленным.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="7cbc3-109">Например, результат 7 / 3 равняется 2.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="7cbc3-110">Чтобы определить остаток от деления 7 / 3, используйте оператор остатка ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7cbc3-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="7cbc3-111">Чтобы получить частное в виде рационального числа или дроби, задайте делителю или делимому тип `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="7cbc3-112">Можно назначить тип неявно, если выразить делимое или делитель в десятичном формате, поместив цифру справа от десятичной запятой, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbc3-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cbc3-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7cbc3-113">Example</span></span>  
 <span data-ttu-id="7cbc3-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7cbc3-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbc3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7cbc3-115">See Also</span></span>  
 <span data-ttu-id="7cbc3-116">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7cbc3-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7cbc3-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7cbc3-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7cbc3-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="7cbc3-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

