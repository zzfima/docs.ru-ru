---
title: "Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 223b3fc84fe75d1d530cd182c9332e5c663aa519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="c8be2-102">Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8be2-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="c8be2-103">При использовании класса или структуры, определяющей свои собственные операторы, доступ к этим операторам из [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8be2-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="c8be2-104">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="c8be2-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8be2-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c8be2-105">Example</span></span>  
 <span data-ttu-id="c8be2-106">Следующий пример обращается к структуре SQL <xref:System.Data.SqlTypes.SqlString>, который определяет операторы преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] строки.</span><span class="sxs-lookup"><span data-stu-id="c8be2-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string.</span></span> <span data-ttu-id="c8be2-107">Используйте `CType(` *строковое выражение SQL*, `String)` для преобразования строки SQL для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] строку, и `CType(` *строковое выражение Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` для преобразования в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="c8be2-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <span data-ttu-id="c8be2-108"><xref:System.Data.SqlTypes.SqlString> Структура определяет оператор преобразования ([функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) из `String` для <xref:System.Data.SqlTypes.SqlString> , а другой из <xref:System.Data.SqlTypes.SqlString> для `String`.</span><span class="sxs-lookup"><span data-stu-id="c8be2-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="c8be2-109">Оператор, который присваивает `title` для `jobTitle` использует первый оператор и <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов функции используется второй.</span><span class="sxs-lookup"><span data-stu-id="c8be2-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8be2-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c8be2-110">Compiling the Code</span></span>  
 <span data-ttu-id="c8be2-111">Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="c8be2-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="c8be2-112">Не следует предполагать, что класс или структура определяет каждый оператор доступный для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="c8be2-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="c8be2-113">Список доступных операторов см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8be2-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="c8be2-114">Включите соответствующий `Imports` инструкции для строки SQL в начале файла исходного кода (в данном случае <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="c8be2-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="c8be2-115">Проект должен иметь ссылки на System.Data и System.XML.</span><span class="sxs-lookup"><span data-stu-id="c8be2-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8be2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c8be2-116">See Also</span></span>  
 [<span data-ttu-id="c8be2-117">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="c8be2-117">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="c8be2-118">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="c8be2-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="c8be2-119">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="c8be2-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="c8be2-120">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="c8be2-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="c8be2-121">Расширение</span><span class="sxs-lookup"><span data-stu-id="c8be2-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="c8be2-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="c8be2-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="c8be2-123">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="c8be2-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="c8be2-124">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="c8be2-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="c8be2-125">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="c8be2-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="c8be2-126">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="c8be2-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
