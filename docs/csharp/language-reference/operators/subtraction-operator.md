---
title: '- Оператор (ссылка C#)'
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: ed4c46d21be41762f875ff38ceded8919112b6d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271080"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="22436-102">Оператор — (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="22436-102">- Operator (C# Reference)</span></span>
<span data-ttu-id="22436-103">Оператор `-` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="22436-103">The `-` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22436-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="22436-104">Remarks</span></span>  
 <span data-ttu-id="22436-105">Унарные операторы `-` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="22436-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="22436-106">Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.</span><span class="sxs-lookup"><span data-stu-id="22436-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>  
  
 <span data-ttu-id="22436-107">Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.</span><span class="sxs-lookup"><span data-stu-id="22436-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>  
  
 <span data-ttu-id="22436-108">Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.</span><span class="sxs-lookup"><span data-stu-id="22436-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>  
  
 <span data-ttu-id="22436-109">Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="22436-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="22436-110">Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="22436-110">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22436-111">Пример</span><span class="sxs-lookup"><span data-stu-id="22436-111">Example</span></span>  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="22436-112">См. также</span><span class="sxs-lookup"><span data-stu-id="22436-112">See Also</span></span>  
 [<span data-ttu-id="22436-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="22436-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="22436-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="22436-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="22436-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="22436-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
