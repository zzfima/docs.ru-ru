---
title: "Операторы объединения в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f255e168b9eb794ef846e0cc18dbbdba5941bec5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="f0ae2-102">Операторы объединения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0ae2-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="f0ae2-103">Операторы объединения объединяют несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="f0ae2-104">Существует два оператора объединения: `+` и `&`.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="f0ae2-105">Оба они выполняют базовую операцию объединения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="f0ae2-106">Эти операторы также могут объединять переменные `String`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 <span data-ttu-id="f0ae2-107">[!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0ae2-107">[!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span></span>  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="f0ae2-108">Различия между двумя операторами объединения</span><span class="sxs-lookup"><span data-stu-id="f0ae2-108">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="f0ae2-109">[Оператор +](../../../../visual-basic/language-reference/operators/addition-operator.md) имеет основной целью сложения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-109">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="f0ae2-110">Однако он также может объединять числовые операнды со строковыми.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-110">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="f0ae2-111">`+` Оператор имеет сложный набор правил, определяющих, следует ли добавлять, объединять, сообщить об ошибке компилятора или исключение времени выполнения <xref:System.InvalidCastException>исключение.</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="f0ae2-111">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="f0ae2-112">[& Оператор](../../../../visual-basic/language-reference/operators/concatenation-operator.md) определяется только для `String` операнда и всегда расширяет свои операнды до `String`, независимо от параметра `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-112">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="f0ae2-113">Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.</span><span class="sxs-lookup"><span data-stu-id="f0ae2-113">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="f0ae2-114">Производительность: String и StringBuilder</span><span class="sxs-lookup"><span data-stu-id="f0ae2-114">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="f0ae2-115">Если вы выполняете множество манипуляций со строками, как объединения, удаления и замены, производительность можно увеличить с <xref:System.Text.StringBuilder>класса в <xref:System.Text>имен.</xref:System.Text> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="f0ae2-115">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="f0ae2-116">Требуется дополнительная инструкция для создания и инициализации <xref:System.Text.StringBuilder>объекта и еще один оператор для преобразования итогового значения для `String`, но на этот раз можно восстановить, так как <xref:System.Text.StringBuilder>может работать быстрее.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="f0ae2-116">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ae2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0ae2-117">See Also</span></span>  
 <span data-ttu-id="f0ae2-118">[Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f0ae2-118">[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="f0ae2-119"> [Типы методов для обработки в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f0ae2-119"> [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span></span>  
<span data-ttu-id="f0ae2-120"> [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="f0ae2-120"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="f0ae2-121"> [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="f0ae2-121"> [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="f0ae2-122"> [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="f0ae2-122"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
