---
title: "Оператор () (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d62e6c93dcc69c892d4ca96ace3806cb1c8d989
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1165e-102">Оператор () (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1165e-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="1165e-103">Помимо использования для указания порядка операций в выражении круглые скобки используются для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="1165e-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="1165e-104">Задание операций приведения или преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="1165e-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="1165e-105">Вызов методов или делегатов.</span><span class="sxs-lookup"><span data-stu-id="1165e-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="1165e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1165e-106">Remarks</span></span>  
 <span data-ttu-id="1165e-107">Приведение явно вызывает оператор преобразования из одного типа в другой. Если такой оператор преобразования не определен, приведение завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="1165e-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="1165e-108">Сведения об определении оператора преобразования см. в разделах [explicit](../../../csharp/language-reference/keywords/explicit.md) и [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="1165e-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="1165e-109">Оператор `()` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="1165e-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="1165e-110">Дополнительные сведения см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1165e-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="1165e-111">Выражение приведения может обуславливать неоднозначный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="1165e-111">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="1165e-112">Например, выражение `(x)–y` может интерпретироваться как выражение приведения (приведение –y к типу x) или как выражение добавления в сочетании с выражением в скобках, которое вычисляет значение x – y.</span><span class="sxs-lookup"><span data-stu-id="1165e-112">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="1165e-113">Дополнительные сведения о вызове методов см. в разделе [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="1165e-113">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1165e-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1165e-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1165e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1165e-115">See Also</span></span>  
 [<span data-ttu-id="1165e-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1165e-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1165e-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1165e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1165e-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="1165e-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
