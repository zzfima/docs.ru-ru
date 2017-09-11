---
title: "Практическое руководство: возвращение значения из процедуры (Visual Basic) | Документы Microsoft"
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
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.openlocfilehash: 601cd3adca0105eb829bb6156f94289b5c9f5f72
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="de4ff-102">Практическое руководство. Возврат значения из процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de4ff-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="de4ff-103">Объект `Function` процедура возвращает значение в вызывающий код либо путем выполнения `Return` инструкции или путем добавления `Exit Function` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="de4ff-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="de4ff-104">Для возврата значения с помощью инструкции Return</span><span class="sxs-lookup"><span data-stu-id="de4ff-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="de4ff-105">Поместите `Return` инструкции в точку, где завершена задача процедуры.</span><span class="sxs-lookup"><span data-stu-id="de4ff-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="de4ff-106">Выполните `Return` ключевого слова и выражения, возвращающего значение требуется вернуться к вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="de4ff-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="de4ff-107">Можно иметь несколько `Return` инструкции в той же процедуре.</span><span class="sxs-lookup"><span data-stu-id="de4ff-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="de4ff-108">Следующие `Function` процедура вычисляет самая длинная сторона, гипотенуза прямоугольного треугольника и возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="de4ff-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     <span data-ttu-id="de4ff-109">[!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="de4ff-109">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="de4ff-110">В следующем примере показано типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="de4ff-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     <span data-ttu-id="de4ff-111">[!code-vb[VbVbcnProcedures №&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="de4ff-111">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span></span>  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="de4ff-112">Для возврата значения с помощью Exit Function или End Function</span><span class="sxs-lookup"><span data-stu-id="de4ff-112">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="de4ff-113">В по крайней мере в одном месте `Function` процедура, назначьте ему имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="de4ff-113">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="de4ff-114">При выполнении `Exit Function` или `End Function` инструкции, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] возвращает значение, назначенное имени процедуры наиболее недавно.</span><span class="sxs-lookup"><span data-stu-id="de4ff-114">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="de4ff-115">Можно иметь несколько `Exit Function` инструкции в той же процедуре и можно смешивать `Return` и `Exit Function` инструкций в той же процедуре.</span><span class="sxs-lookup"><span data-stu-id="de4ff-115">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="de4ff-116">Можно иметь только одну `End Function` инструкции в `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="de4ff-116">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="de4ff-117">Дополнительные сведения и пример см. в разделе «Возвращать значение» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="de4ff-117">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4ff-118">См. также</span><span class="sxs-lookup"><span data-stu-id="de4ff-118">See Also</span></span>  
 <span data-ttu-id="de4ff-119">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-119">[Procedures](./index.md) </span></span>  
<span data-ttu-id="de4ff-120"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-120"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="de4ff-121"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="de4ff-122"> [Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-122"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="de4ff-123"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-123"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="de4ff-124"> [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-124"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="de4ff-125"> [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-125"> [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md) </span></span>  
<span data-ttu-id="de4ff-126"> [Практическое руководство: создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="de4ff-126"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="de4ff-127"> [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="de4ff-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
