---
title: "Оператор () (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="ec629-102">Оператор () (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ec629-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="ec629-103">Помимо использования для указания порядка операций в выражении круглые скобки используются для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="ec629-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="ec629-104">Задание операций приведения или преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="ec629-104">Specify casts, or type conversions.</span></span>  
  
     <span data-ttu-id="ec629-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec629-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span></span>  
  
2.  <span data-ttu-id="ec629-106">Вызов методов или делегатов.</span><span class="sxs-lookup"><span data-stu-id="ec629-106">Invoke methods or delegates.</span></span>  
  
     <span data-ttu-id="ec629-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec629-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec629-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec629-108">Remarks</span></span>  
 <span data-ttu-id="ec629-109">Приведение явно вызывает оператор преобразования из одного типа в другой. Если такой оператор преобразования не определен, приведение завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="ec629-109">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="ec629-110">Сведения об определении оператора преобразования см. в разделах [explicit](../../../csharp/language-reference/keywords/explicit.md) и [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="ec629-110">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="ec629-111">Оператор `()` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="ec629-111">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="ec629-112">Дополнительные сведения см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="ec629-112">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="ec629-113">Выражение приведения может обуславливать неоднозначный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="ec629-113">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="ec629-114">Например, выражение `(x)–y` может интерпретироваться как выражение приведения (приведение –y к типу x) или как выражение добавления в сочетании с выражением в скобках, которое вычисляет значение x – y.</span><span class="sxs-lookup"><span data-stu-id="ec629-114">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="ec629-115">Дополнительные сведения о вызове методов см. в разделе [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="ec629-115">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ec629-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ec629-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec629-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ec629-117">See Also</span></span>  
 <span data-ttu-id="ec629-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec629-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ec629-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec629-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ec629-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="ec629-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

