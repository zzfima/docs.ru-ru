---
title: Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197566"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="865cb-102">Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции</span><span class="sxs-lookup"><span data-stu-id="865cb-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="865cb-103">Вычисление функции отключено, так как истекло время ожидания при вычислении предыдущей функции. Чтобы повторно включить вычисление функции, повторите шаг или перезапустите отладку.</span><span class="sxs-lookup"><span data-stu-id="865cb-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="865cb-104">В отладчике Visual Studio выражение указывает вызов процедуры, но время ожидания для другого вычисления истекло.</span><span class="sxs-lookup"><span data-stu-id="865cb-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="865cb-105">Возможные причины истечения времени ожидания вызова процедуры включают бесконечный цикл или *бесконечный цикл*.</span><span class="sxs-lookup"><span data-stu-id="865cb-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="865cb-106">Дополнительные сведения см. в разделе [for... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="865cb-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="865cb-107">Особый случай бесконечного цикла — *рекурсия*.</span><span class="sxs-lookup"><span data-stu-id="865cb-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="865cb-108">Дополнительные сведения см. в разделе [Рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="865cb-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="865cb-109">**Идентификатор ошибки:** BC30957</span><span class="sxs-lookup"><span data-stu-id="865cb-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="865cb-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="865cb-110">To correct this error</span></span>  
  
1. <span data-ttu-id="865cb-111">По возможности определите, что использовалось предыдущее вычисление функции и что привело к истечению времени ожидания. В противном случае эта ошибка может возникать снова.</span><span class="sxs-lookup"><span data-stu-id="865cb-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="865cb-112">Либо пошаговый отладчик снова, либо завершите и перезапустите отладку.</span><span class="sxs-lookup"><span data-stu-id="865cb-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="865cb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="865cb-113">See also</span></span>

- [<span data-ttu-id="865cb-114">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="865cb-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="865cb-115">Навигация по коду с помощью отладчика</span><span class="sxs-lookup"><span data-stu-id="865cb-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
