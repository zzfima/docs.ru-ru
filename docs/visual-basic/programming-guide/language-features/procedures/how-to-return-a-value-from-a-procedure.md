---
title: Практическое руководство. Возврат значения из процедуры (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: affcb25951a6647604286bc91dcaec8898fe2e30
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="88139-102">Практическое руководство. Возврат значения из процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88139-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="88139-103">Объект `Function` процедура возвращает значение вызывающему коду либо выполнив `Return` инструкции или путем добавления `Exit Function` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="88139-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="88139-104">Для возврата значения с помощью инструкции Return</span><span class="sxs-lookup"><span data-stu-id="88139-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="88139-105">Поместите `Return` инструкции в той точке, где выполняется задача процедуры.</span><span class="sxs-lookup"><span data-stu-id="88139-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="88139-106">Выполните `Return` ключевое слово с помощью выражения, возвращающего значение, можно вернуться в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="88139-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="88139-107">В одной и той же процедуре можно использовать несколько операторов `Return`.</span><span class="sxs-lookup"><span data-stu-id="88139-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="88139-108">Следующие `Function` процедура рассчитывается длинной стороны, гипотенуза прямоугольного треугольника и возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="88139-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="88139-109">В примере показан типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="88139-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="88139-110">Для возврата значения с помощью Exit Function или End Function</span><span class="sxs-lookup"><span data-stu-id="88139-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="88139-111">В по крайней мере в одном месте `Function` процедуры, назначить значение имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="88139-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="88139-112">При выполнении `Exit Function` или `End Function` оператор, Visual Basic возвращает значение самого последнего назначения для имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="88139-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="88139-113">В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="88139-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="88139-114">Может быть только один `End Function` инструкции в `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="88139-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="88139-115">Дополнительные сведения и пример см. в разделе «Возвращение значения» в [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="88139-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88139-116">См. также</span><span class="sxs-lookup"><span data-stu-id="88139-116">See Also</span></span>  
 [<span data-ttu-id="88139-117">Процедуры</span><span class="sxs-lookup"><span data-stu-id="88139-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="88139-118">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="88139-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="88139-119">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="88139-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="88139-120">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="88139-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="88139-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="88139-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="88139-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="88139-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="88139-123">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="88139-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="88139-124">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="88139-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="88139-125">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="88139-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
