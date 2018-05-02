---
title: Оператор / (Справочник по C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b17d122e3e3f75012e084903b6f8975fb53d46c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="60b4c-102">Оператор / (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="60b4c-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="60b4c-103">Оператор деления (`/`) делит первый операнд на второй.</span><span class="sxs-lookup"><span data-stu-id="60b4c-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="60b4c-104">Все числовые типы имеют предопределенные операторы деления.</span><span class="sxs-lookup"><span data-stu-id="60b4c-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="60b4c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="60b4c-105">Remarks</span></span>  
 <span data-ttu-id="60b4c-106">Определяемые пользователем типы могут вызвать перегрузку оператора `/` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="60b4c-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="60b4c-107">Перегрузка оператора `/` неявно перегружает [ оператор /= ](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="60b4c-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="60b4c-108">При делении двух целых чисел результат всегда является целочисленным.</span><span class="sxs-lookup"><span data-stu-id="60b4c-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="60b4c-109">Например, результат 7 / 3 равняется 2.</span><span class="sxs-lookup"><span data-stu-id="60b4c-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="60b4c-110">Эту операцию не следует путать с делением с округлением к меньшему, так как оператор `/` производит округление в торону нуля: –7/3 равно –2.</span><span class="sxs-lookup"><span data-stu-id="60b4c-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="60b4c-111">Чтобы получить частное в виде рационального числа, используйте тип `float`, `double` или `decimal`.</span><span class="sxs-lookup"><span data-stu-id="60b4c-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="60b4c-112">Существует множество способов преобразования между [встроенными числовыми типами](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="60b4c-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="60b4c-113">Чтобы определить остаток, используйте [оператор остатка](../../../csharp/language-reference/operators/remainder-operator.md) (`%`).</span><span class="sxs-lookup"><span data-stu-id="60b4c-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60b4c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="60b4c-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="60b4c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="60b4c-115">See Also</span></span>  
 [<span data-ttu-id="60b4c-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="60b4c-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="60b4c-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="60b4c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="60b4c-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="60b4c-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
