---
title: Оператор Throw (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: c17adc6df0f8cf94f06547b48a32b2ffb8f303ca
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973487"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="c14dc-102">Оператор Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c14dc-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="c14dc-103">Возникло исключение в процедуре.</span><span class="sxs-lookup"><span data-stu-id="c14dc-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c14dc-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="c14dc-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="c14dc-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="c14dc-106">Сведения об исключении исключение.</span><span class="sxs-lookup"><span data-stu-id="c14dc-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="c14dc-107">Необязательно, если находятся в `Catch` инструкции, в противном случае необходимо.</span><span class="sxs-lookup"><span data-stu-id="c14dc-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c14dc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c14dc-108">Remarks</span></span>  
 <span data-ttu-id="c14dc-109">`Throw` Оператор создает исключение, которое можно обработать с помощью структурированный код обработки исключений (`Try`... `Catch`... `Finally`) или неструктурированных код обработки исключений (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="c14dc-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="c14dc-110">Можно использовать `Throw` инструкции для перехвата ошибок в коде, поскольку Visual Basic перемещается вверх по стеку вызовов, пока не найдет соответствующий код обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="c14dc-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="c14dc-111">Объект `Throw` оператор выражения не может использоваться только в `Catch` инструкции, в котором операторе case повторно вызывает исключение, обрабатываемое в данный момент `Catch` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c14dc-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="c14dc-112">`Throw` Инструкция сбрасывает стек вызовов для `expression` исключение.</span><span class="sxs-lookup"><span data-stu-id="c14dc-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="c14dc-113">Если `expression` не указан, стек вызовов останется без изменений.</span><span class="sxs-lookup"><span data-stu-id="c14dc-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="c14dc-114">Можно получить доступ к стек вызовов для исключения через <xref:System.Exception.StackTrace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="c14dc-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14dc-115">Пример</span><span class="sxs-lookup"><span data-stu-id="c14dc-115">Example</span></span>  
 <span data-ttu-id="c14dc-116">В следующем коде используется `Throw` инструкции для создания исключения:</span><span class="sxs-lookup"><span data-stu-id="c14dc-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a><span data-ttu-id="c14dc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c14dc-117">Requirements</span></span>  
 <span data-ttu-id="c14dc-118">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="c14dc-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="c14dc-119">**Модуль:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="c14dc-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="c14dc-120">**Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="c14dc-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14dc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c14dc-121">See also</span></span>
- [<span data-ttu-id="c14dc-122">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="c14dc-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="c14dc-123">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="c14dc-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
