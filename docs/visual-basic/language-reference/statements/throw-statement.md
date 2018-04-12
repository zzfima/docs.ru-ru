---
title: Оператор Throw (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="e6a34-102">Оператор Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6a34-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="e6a34-103">Вызывает исключение в процедуре.</span><span class="sxs-lookup"><span data-stu-id="e6a34-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6a34-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="e6a34-105">Отделение</span><span class="sxs-lookup"><span data-stu-id="e6a34-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="e6a34-106">Сведения о к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="e6a34-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="e6a34-107">Необязательно, если в `Catch` инструкции, в противном случае необходимо.</span><span class="sxs-lookup"><span data-stu-id="e6a34-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6a34-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6a34-108">Remarks</span></span>  
 <span data-ttu-id="e6a34-109">`Throw` Оператор создает исключение, которое можно обработать с помощью кода структурированной обработки исключений (`Try`... `Catch`... `Finally`) или неструктурированных код обработки исключений (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="e6a34-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="e6a34-110">Можно использовать `Throw` инструкции для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов, пока не найдет соответствующий код обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="e6a34-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="e6a34-111">Объект `Throw` оператор без выражения может использоваться только в `Catch` инструкции, исключение обрабатываемое в данный момент повторно создает инструкцию случай `Catch` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e6a34-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="e6a34-112">`Throw` Инструкция сбрасывает стек вызовов для `expression` исключения.</span><span class="sxs-lookup"><span data-stu-id="e6a34-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="e6a34-113">Если `expression` не указано, стек вызовов останется без изменений.</span><span class="sxs-lookup"><span data-stu-id="e6a34-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="e6a34-114">Можно получить доступ к стек вызовов для исключения через <xref:System.Exception.StackTrace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e6a34-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a34-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e6a34-115">Example</span></span>  
 <span data-ttu-id="e6a34-116">В следующем коде используется `Throw` инструкции для создания исключения:</span><span class="sxs-lookup"><span data-stu-id="e6a34-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="e6a34-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e6a34-117">Requirements</span></span>  
 <span data-ttu-id="e6a34-118">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="e6a34-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="e6a34-119">**Модуль:**`Interaction`</span><span class="sxs-lookup"><span data-stu-id="e6a34-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="e6a34-120">**Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="e6a34-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a34-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e6a34-121">See Also</span></span>  
 [<span data-ttu-id="e6a34-122">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e6a34-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="e6a34-123">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="e6a34-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
