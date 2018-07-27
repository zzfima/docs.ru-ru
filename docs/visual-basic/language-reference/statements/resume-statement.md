---
title: Resume-оператор (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 853f3fe060b70c8a43957d3c843fb95539981679
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39296160"
---
# <a name="resume-statement"></a><span data-ttu-id="8d5fd-102">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="8d5fd-102">Resume Statement</span></span>
<span data-ttu-id="8d5fd-103">Возобновляет выполнение после завершения процедуры обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="8d5fd-104">Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="8d5fd-105">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d5fd-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d5fd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d5fd-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8d5fd-107">Части</span><span class="sxs-lookup"><span data-stu-id="8d5fd-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="8d5fd-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-108">Required.</span></span> <span data-ttu-id="8d5fd-109">Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, который вызвал ошибку.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="8d5fd-110">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="8d5fd-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-111">Optional.</span></span> <span data-ttu-id="8d5fd-112">Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, следующего инструкцию, которая вызвала ошибку.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="8d5fd-113">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, следующего оператора, который последним вызвал процедуру, содержащую обработчик ошибок (или `On Error Resume Next` инструкции).</span><span class="sxs-lookup"><span data-stu-id="8d5fd-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="8d5fd-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-114">Optional.</span></span> <span data-ttu-id="8d5fd-115">Выполнение возобновляется строки, указанной в обязательном `line` аргумент.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="8d5fd-116">`line` Аргумент представляет собой метку или номер строки и должно быть в той же процедуре в качестве обработчика ошибок.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d5fd-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d5fd-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d5fd-118">Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="8d5fd-119">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8d5fd-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="8d5fd-120">Если вы используете `Resume` инструкции в любом отличное от в процедуру обработки ошибок, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="8d5fd-121">`Resume` Оператор не может использоваться в любой процедуре, которая содержит `Try...Catch...Finally` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d5fd-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8d5fd-122">Example</span></span>  
 <span data-ttu-id="8d5fd-123">В этом примере используется `Resume` инструкцию, чтобы завершить обработку ошибок в процедуре и затем возобновить выполнение с помощью инструкции, которая вызвала ошибку.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="8d5fd-124">Чтобы проиллюстрировать использование создается ошибка номер 55 `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8d5fd-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="8d5fd-125">Требования</span><span class="sxs-lookup"><span data-stu-id="8d5fd-125">Requirements</span></span>  
 <span data-ttu-id="8d5fd-126">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="8d5fd-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="8d5fd-127">**Сборка:** библиотеки времени выполнения Visual Basic (в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="8d5fd-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5fd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8d5fd-128">See Also</span></span>  
 [<span data-ttu-id="8d5fd-129">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="8d5fd-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="8d5fd-130">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="8d5fd-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="8d5fd-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="8d5fd-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
