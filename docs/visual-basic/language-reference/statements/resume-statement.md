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
ms.openlocfilehash: fcb50a9c7e36bab046be25d7f82f91cfe0f9be8e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966922"
---
# <a name="resume-statement"></a><span data-ttu-id="08c3b-102">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="08c3b-102">Resume Statement</span></span>
<span data-ttu-id="08c3b-103">Возобновляет выполнение после завершения процедуры обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="08c3b-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="08c3b-104">Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций.</span><span class="sxs-lookup"><span data-stu-id="08c3b-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="08c3b-105">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08c3b-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c3b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08c3b-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="08c3b-107">Части</span><span class="sxs-lookup"><span data-stu-id="08c3b-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="08c3b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="08c3b-108">Required.</span></span> <span data-ttu-id="08c3b-109">Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, который вызвал ошибку.</span><span class="sxs-lookup"><span data-stu-id="08c3b-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="08c3b-110">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="08c3b-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="08c3b-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="08c3b-111">Optional.</span></span> <span data-ttu-id="08c3b-112">Если ошибка произошла в той же процедуре, обработчик ошибок, выполнение возобновляется с оператора, следующего инструкцию, которая вызвала ошибку.</span><span class="sxs-lookup"><span data-stu-id="08c3b-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="08c3b-113">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, следующего оператора, который последним вызвал процедуру, содержащую обработчик ошибок (или `On Error Resume Next` инструкции).</span><span class="sxs-lookup"><span data-stu-id="08c3b-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="08c3b-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="08c3b-114">Optional.</span></span> <span data-ttu-id="08c3b-115">Выполнение возобновляется строки, указанной в обязательном `line` аргумент.</span><span class="sxs-lookup"><span data-stu-id="08c3b-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="08c3b-116">`line` Аргумент представляет собой метку или номер строки и должно быть в той же процедуре в качестве обработчика ошибок.</span><span class="sxs-lookup"><span data-stu-id="08c3b-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08c3b-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="08c3b-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08c3b-118">Мы рекомендуем использовать структурированной обработки исключений в коде, когда это возможно, а не с помощью неструктурированной обработки исключений и `On Error` и `Resume` инструкций.</span><span class="sxs-lookup"><span data-stu-id="08c3b-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="08c3b-119">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08c3b-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="08c3b-120">Если вы используете `Resume` инструкции в любом отличное от в процедуру обработки ошибок, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="08c3b-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="08c3b-121">`Resume` Оператор не может использоваться в любой процедуре, которая содержит `Try...Catch...Finally` инструкции.</span><span class="sxs-lookup"><span data-stu-id="08c3b-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c3b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="08c3b-122">Example</span></span>  
 <span data-ttu-id="08c3b-123">В этом примере используется `Resume` инструкцию, чтобы завершить обработку ошибок в процедуре и затем возобновить выполнение с помощью инструкции, которая вызвала ошибку.</span><span class="sxs-lookup"><span data-stu-id="08c3b-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="08c3b-124">Чтобы проиллюстрировать использование создается ошибка номер 55 `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="08c3b-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="08c3b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="08c3b-125">Requirements</span></span>  
 <span data-ttu-id="08c3b-126">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="08c3b-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="08c3b-127">**Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="08c3b-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c3b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="08c3b-128">See also</span></span>
- [<span data-ttu-id="08c3b-129">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="08c3b-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="08c3b-130">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="08c3b-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="08c3b-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="08c3b-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
