---
title: '- Оператор (ссылка C#)'
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: bd852f96ece9c8d5d5e2ec42e802596e795ce04a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43393432"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="93fff-102">Оператор — (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="93fff-102">- Operator (C# Reference)</span></span>
<span data-ttu-id="93fff-103">Оператор `-` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="93fff-103">The `-` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93fff-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="93fff-104">Remarks</span></span>  
 <span data-ttu-id="93fff-105">Унарные операторы `-` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="93fff-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="93fff-106">Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.</span><span class="sxs-lookup"><span data-stu-id="93fff-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>  
  
 <span data-ttu-id="93fff-107">Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.</span><span class="sxs-lookup"><span data-stu-id="93fff-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>  
  
 <span data-ttu-id="93fff-108">Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.</span><span class="sxs-lookup"><span data-stu-id="93fff-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>  
  
 <span data-ttu-id="93fff-109">Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="93fff-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="93fff-110">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="93fff-110">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93fff-111">Пример</span><span class="sxs-lookup"><span data-stu-id="93fff-111">Example</span></span>  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="93fff-112">См. также</span><span class="sxs-lookup"><span data-stu-id="93fff-112">See Also</span></span>

- [<span data-ttu-id="93fff-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="93fff-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="93fff-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="93fff-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="93fff-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="93fff-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
