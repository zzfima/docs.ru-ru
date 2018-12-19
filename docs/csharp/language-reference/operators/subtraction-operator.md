---
title: '- Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 5a467e8383d7510260ad3044976601deca7cafdb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242234"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="de41b-102">Оператор — (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="de41b-102">- Operator (C# Reference)</span></span>
<span data-ttu-id="de41b-103">Оператор `-` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="de41b-103">The `-` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de41b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="de41b-104">Remarks</span></span>  
 <span data-ttu-id="de41b-105">Унарные операторы `-` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="de41b-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="de41b-106">Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.</span><span class="sxs-lookup"><span data-stu-id="de41b-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>  
  
 <span data-ttu-id="de41b-107">Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.</span><span class="sxs-lookup"><span data-stu-id="de41b-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>  
  
 <span data-ttu-id="de41b-108">Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.</span><span class="sxs-lookup"><span data-stu-id="de41b-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>  
  
 <span data-ttu-id="de41b-109">Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="de41b-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="de41b-110">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="de41b-110">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="de41b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="de41b-111">Example</span></span>  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="de41b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="de41b-112">See Also</span></span>

- [<span data-ttu-id="de41b-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="de41b-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="de41b-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="de41b-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="de41b-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="de41b-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
