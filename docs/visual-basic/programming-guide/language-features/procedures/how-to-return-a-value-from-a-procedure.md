---
title: Практическое руководство. Возвращение значения из процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 293234346053034b544866b6a2eff84974d8a02b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824563"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="77503-102">Практическое руководство. Возвращение значения из процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77503-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="77503-103">Объект `Function` процедура возвращает значение вызывающему коду, выполнив `Return` инструкции или путем добавления `Exit Function` или `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="77503-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="77503-104">Для возврата значения с помощью инструкции Return</span><span class="sxs-lookup"><span data-stu-id="77503-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="77503-105">Поместите `Return` инструкции в точке, где процедуры завершения.</span><span class="sxs-lookup"><span data-stu-id="77503-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="77503-106">Выполните `Return` ключевое слово с выражением, возвращающего значение, который необходимо вернуть вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="77503-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="77503-107">В одной и той же процедуре можно использовать несколько операторов `Return`.</span><span class="sxs-lookup"><span data-stu-id="77503-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="77503-108">Следующие `Function` процедура рассчитывается самая длинная сторона, гипотенуза прямоугольного треугольника и возвращает его вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="77503-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="77503-109">В следующем примере показано типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="77503-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="77503-110">Для возврата значения с помощью Exit Function или End Function</span><span class="sxs-lookup"><span data-stu-id="77503-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="77503-111">В по крайней мере в одном месте в `Function` процедуры, назначить значение для имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="77503-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="77503-112">При выполнении `Exit Function` или `End Function` инструкция, Visual Basic возвращает наиболее недавно значение имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="77503-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="77503-113">В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="77503-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="77503-114">Может иметь только один `End Function` инструкции в `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="77503-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="77503-115">Дополнительные сведения и пример см. в разделе «Возвращают значение» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77503-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77503-116">См. также</span><span class="sxs-lookup"><span data-stu-id="77503-116">See also</span></span>

- [<span data-ttu-id="77503-117">Процедуры</span><span class="sxs-lookup"><span data-stu-id="77503-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="77503-118">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="77503-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="77503-119">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="77503-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="77503-120">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="77503-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="77503-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="77503-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="77503-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="77503-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="77503-123">Оператор Return</span><span class="sxs-lookup"><span data-stu-id="77503-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="77503-124">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="77503-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="77503-125">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="77503-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
