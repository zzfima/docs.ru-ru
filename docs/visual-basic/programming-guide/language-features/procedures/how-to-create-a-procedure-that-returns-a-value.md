---
title: Как выполнить Создание процедуры, возвращающей значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 18becfe05da27e538c5c294b26e0bb7aa19cad2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506424"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="fa91b-102">Как выполнить Создание процедуры, возвращающей значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa91b-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="fa91b-103">Использовании `Function` процедуры возвращают значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="fa91b-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="fa91b-104">Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="fa91b-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="fa91b-105">Вне любых других процедур используйте `Function` , применив инструкцию `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="fa91b-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="fa91b-106">В `Function` инструкции, следуйте `Function` ключевое слово с именем процедуры, а затем список параметров в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="fa91b-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="fa91b-107">Круглые скобки, используя `As` предложение, чтобы указать тип данных возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="fa91b-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="fa91b-108">Поместите операторы кода процедуры между `Function` и `End Function` инструкций.</span><span class="sxs-lookup"><span data-stu-id="fa91b-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="fa91b-109">Используйте `Return` инструкция возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="fa91b-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="fa91b-110">Следующие `Function` процедура вычисляет самая длинная сторона гипотенузы прямоугольного треугольника, значения для двух других сторон.</span><span class="sxs-lookup"><span data-stu-id="fa91b-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="fa91b-111">В следующем примере показано типичный вызов `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="fa91b-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fa91b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fa91b-112">See also</span></span>
- [<span data-ttu-id="fa91b-113">Процедуры</span><span class="sxs-lookup"><span data-stu-id="fa91b-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fa91b-114">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="fa91b-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fa91b-115">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="fa91b-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fa91b-116">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="fa91b-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="fa91b-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="fa91b-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fa91b-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="fa91b-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="fa91b-119">Практическое руководство. Возвращение значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="fa91b-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="fa91b-120">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="fa91b-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
