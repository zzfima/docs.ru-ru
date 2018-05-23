---
title: Оператор = (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 979250c91cfe2abdf7295ae3866cd6b4294285cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="84c2b-102">Оператор = (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="84c2b-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="84c2b-103">Оператор присваивания (`=`) сохраняет значение расположенного в правой части операнда в месте хранения, свойстве или индексаторе, которые указаны в операнде слева, после чего возвращает значение в виде результата.</span><span class="sxs-lookup"><span data-stu-id="84c2b-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="84c2b-104">Операнды должны иметь один тип (либо операнд справа должен допускать неявное преобразование в тип операнда в левой части).</span><span class="sxs-lookup"><span data-stu-id="84c2b-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c2b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="84c2b-105">Remarks</span></span>  
 <span data-ttu-id="84c2b-106">Оператор присваивания нельзя перегружать.</span><span class="sxs-lookup"><span data-stu-id="84c2b-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="84c2b-107">Тем не менее можно определить операторы неявного преобразования типа, которые позволяют использовать оператор присваивания с этими типами.</span><span class="sxs-lookup"><span data-stu-id="84c2b-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="84c2b-108">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="84c2b-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84c2b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="84c2b-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="84c2b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="84c2b-110">See Also</span></span>  
 [<span data-ttu-id="84c2b-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="84c2b-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="84c2b-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="84c2b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="84c2b-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="84c2b-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
