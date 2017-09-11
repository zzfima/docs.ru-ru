---
title: "Практическое руководство: использование класс, который определяет операторы (Visual Basic) | Документы Microsoft"
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
- operator procedures, calling
- procedures, operator
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
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
ms.openlocfilehash: e4d76788346e08123102d56088c0a1e0f5f2238f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="58e0a-102">Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58e0a-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="58e0a-103">При использовании класса или структуры, определяющей свои собственные операторы, можно получить доступ к этим операторам из [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="58e0a-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="58e0a-104">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="58e0a-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e0a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="58e0a-105">Example</span></span>  
 <span data-ttu-id="58e0a-106">Следующий пример обращается к структуре SQL <xref:System.Data.SqlTypes.SqlString>, который определяет операторы преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] строки.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="58e0a-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string.</span></span> <span data-ttu-id="58e0a-107">Используйте `CType(` *строковое выражение SQL*, `String)` для преобразования строки SQL для [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] строку, и `CType(` *строковое выражение Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` для преобразования в другом направлении.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="58e0a-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 <span data-ttu-id="58e0a-108">[!code-vb[VbVbcnProcedures&#30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="58e0a-108">[!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="58e0a-109">[!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="58e0a-109">[!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="58e0a-110"><xref:System.Data.SqlTypes.SqlString>Структура определяет оператор преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) из `String` для <xref:System.Data.SqlTypes.SqlString>и <xref:System.Data.SqlTypes.SqlString>для `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="58e0a-110">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="58e0a-111">Оператор, который присваивает `title` для `jobTitle` использует первый оператор и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>вызова функции используется второй.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="58e0a-111">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58e0a-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="58e0a-112">Compiling the Code</span></span>  
 <span data-ttu-id="58e0a-113">Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="58e0a-113">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="58e0a-114">Не следует предполагать, что класс или структура определяет каждый оператор, доступный для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="58e0a-114">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="58e0a-115">Список доступных операторов см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="58e0a-115">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="58e0a-116">Включить соответствующую `Imports` инструкции для строки SQL в начале файла исходного кода (в данном случае <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="58e0a-116">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="58e0a-117">Проект должен иметь ссылки на System.Data и System.XML.</span><span class="sxs-lookup"><span data-stu-id="58e0a-117">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e0a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="58e0a-118">See Also</span></span>  
 <span data-ttu-id="58e0a-119">[Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-119">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="58e0a-120"> [Практическое руководство: определение оператора](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-120"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="58e0a-121"> [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-121"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="58e0a-122"> [Практическое руководство: вызов процедуры оператора](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-122"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="58e0a-123"> [Расширяющие](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="58e0a-124"> [Сужающие](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-124"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="58e0a-125"> [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-125"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="58e0a-126"> [Практическое руководство: объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-126"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="58e0a-127"> [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="58e0a-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="58e0a-128"> [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="58e0a-128"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
