---
title: Оператор Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 23bb57ec022e62cd586c533d4ed4c792789a0b38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627009"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="545b5-102">Оператор Continue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="545b5-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="545b5-103">Передает управление непосредственно следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="545b5-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="545b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="545b5-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="545b5-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="545b5-105">Remarks</span></span>  
 <span data-ttu-id="545b5-106">Можно перенести из внутри `Do`, `For`, или `While` цикл в следующую итерацию цикла.</span><span class="sxs-lookup"><span data-stu-id="545b5-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="545b5-107">Управление немедленно передается проверке условия цикла, что эквивалентно передаче `For` или `While` инструкции или `Do` или `Loop` инструкция, содержащая `Until` или `While` предложение.</span><span class="sxs-lookup"><span data-stu-id="545b5-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="545b5-108">Можно использовать `Continue` в любом расположении в цикл, который позволяет передачу.</span><span class="sxs-lookup"><span data-stu-id="545b5-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="545b5-109">Правила разрешения передачи элемента управления совпадают с [оператор GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="545b5-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="545b5-110">Например, если цикл полностью содержится в `Try` блока, `Catch` блока или `Finally` блока, можно использовать `Continue` для передачи из цикла.</span><span class="sxs-lookup"><span data-stu-id="545b5-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="545b5-111">Если, с другой стороны, `Try`... `End Try` структура находится внутри цикла, нельзя использовать `Continue` для передачи управления из `Finally` блок и можно использовать для передачи из `Try` или `Catch` блокируется только в том случае, если вы полностью передачи из `Try`... `End Try` структуры.</span><span class="sxs-lookup"><span data-stu-id="545b5-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="545b5-112">Если у вас есть вложенные циклы одного типа, например `Do` цикл в другом `Do` цикл, `Continue Do` инструкция переходит к следующей итерации самого внутреннего `Do` цикл, который его содержит.</span><span class="sxs-lookup"><span data-stu-id="545b5-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="545b5-113">Нельзя использовать `Continue` переходите к следующей итерации цикла, содержащего того же типа.</span><span class="sxs-lookup"><span data-stu-id="545b5-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="545b5-114">Если у вас есть вложенные циклы разных типов, например `Do` цикл в `For` цикла, можно перейти к следующей итерации любого цикла с помощью `Continue Do` или `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="545b5-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="545b5-115">Пример</span><span class="sxs-lookup"><span data-stu-id="545b5-115">Example</span></span>  
 <span data-ttu-id="545b5-116">В следующем примере кода используется `Continue While` инструкцию, чтобы пропустить к следующему столбцу массива, если делитель равен нулю.</span><span class="sxs-lookup"><span data-stu-id="545b5-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="545b5-117">`Continue While` Находится внутри `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="545b5-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="545b5-118">Он передает `While col < lastcol` инструкцию, которая является следующей итерации самого внутреннего `While` цикл, который содержит `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="545b5-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="545b5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="545b5-119">See also</span></span>
- [<span data-ttu-id="545b5-120">Оператор Do...Loop</span><span class="sxs-lookup"><span data-stu-id="545b5-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="545b5-121">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="545b5-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="545b5-122">Оператор While...End While</span><span class="sxs-lookup"><span data-stu-id="545b5-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="545b5-123">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="545b5-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
