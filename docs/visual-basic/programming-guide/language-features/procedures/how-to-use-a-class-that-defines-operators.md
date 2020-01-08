---
title: Практическое руководство. Использование класса, в котором определяются операторы
ms.date: 07/20/2015
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
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347889"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="463c5-102">Практическое руководство. Использование класса, в котором определяются операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="463c5-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="463c5-103">При использовании класса или структуры, определяющей собственные операторы, можно получить доступ к этим операторам из Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="463c5-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="463c5-104">Определение оператора для класса или структуры также называется *перегрузкой* оператора.</span><span class="sxs-lookup"><span data-stu-id="463c5-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="463c5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="463c5-105">Example</span></span>  
 <span data-ttu-id="463c5-106">В следующем примере осуществляется доступ к структуре SQL <xref:System.Data.SqlTypes.SqlString>, которая определяет операторы преобразования ([Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) в обоих направлениях между строкой SQL и строкой Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="463c5-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="463c5-107">Используйте `CType(`*строковое выражение SQL*, `String)` для преобразования строки sql в Visual Basic строку и `CType(`*Visual Basic строкового выражения*<xref:System.Data.SqlTypes.SqlString>`)` для преобразования в другом направлении.</span><span class="sxs-lookup"><span data-stu-id="463c5-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="463c5-108">Структура <xref:System.Data.SqlTypes.SqlString> определяет оператор преобразования ([функцию CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) от `String` до <xref:System.Data.SqlTypes.SqlString>, а другой — от <xref:System.Data.SqlTypes.SqlString> до `String`.</span><span class="sxs-lookup"><span data-stu-id="463c5-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="463c5-109">Инструкция, которая присваивает `title` `jobTitle` использует первый оператор, а <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> вызов функции использует второй метод.</span><span class="sxs-lookup"><span data-stu-id="463c5-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="463c5-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="463c5-110">Compile the code</span></span>  
 <span data-ttu-id="463c5-111">Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="463c5-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="463c5-112">Не следует считать, что класс или структура определили все операторы, доступные для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="463c5-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="463c5-113">Список доступных операторов см. в разделе Оператор [operator](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="463c5-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="463c5-114">Включите соответствующую инструкцию `Imports` для строки SQL в начало исходного файла (в данном случае <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="463c5-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="463c5-115">Проект должен иметь ссылки на System. Data и System. XML.</span><span class="sxs-lookup"><span data-stu-id="463c5-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463c5-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="463c5-116">See also</span></span>

- [<span data-ttu-id="463c5-117">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="463c5-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="463c5-118">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="463c5-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="463c5-119">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="463c5-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="463c5-120">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="463c5-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="463c5-121">Расширение</span><span class="sxs-lookup"><span data-stu-id="463c5-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="463c5-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="463c5-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="463c5-123">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="463c5-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="463c5-124">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="463c5-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="463c5-125">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="463c5-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="463c5-126">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="463c5-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
