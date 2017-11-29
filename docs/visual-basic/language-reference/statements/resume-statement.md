---
title: "Оператор Resume"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb4334f302c07c81b6b8a7d0626be08cc69b1ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="resume-statement"></a><span data-ttu-id="808df-102">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="808df-102">Resume Statement</span></span>
<span data-ttu-id="808df-103">Возобновление выполнения после завершения процедуры обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="808df-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="808df-104">Мы рекомендуем использовать структурированная обработка исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` и `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="808df-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="808df-105">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="808df-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="808df-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="808df-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="808df-107">Части</span><span class="sxs-lookup"><span data-stu-id="808df-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="808df-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="808df-108">Required.</span></span> <span data-ttu-id="808df-109">Если ошибка произошла в той же процедуре обработчик ошибок, выполнение возобновляется с оператора, который вызвал ошибку.</span><span class="sxs-lookup"><span data-stu-id="808df-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="808df-110">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="808df-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="808df-111">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="808df-111">Optional.</span></span> <span data-ttu-id="808df-112">Если ошибка произошла в той же процедуре обработчик ошибок, выполнение возобновляется с оператора, следующего оператора, который вызвал ошибку.</span><span class="sxs-lookup"><span data-stu-id="808df-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="808df-113">Если ошибка возникла в вызываемой процедуре, выполнение возобновляется с оператора, следующего оператора, который последним вызвал процедуру, содержащую обработчик ошибок (или `On Error Resume Next` инструкции).</span><span class="sxs-lookup"><span data-stu-id="808df-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="808df-114">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="808df-114">Optional.</span></span> <span data-ttu-id="808df-115">Выполнение возобновляется строки, указанной в обязательном `line` аргумент.</span><span class="sxs-lookup"><span data-stu-id="808df-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="808df-116">`line` Аргумент представляет собой метку или номер строки и должно быть в той же процедуре обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="808df-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="808df-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="808df-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="808df-118">Мы рекомендуем использовать структурированная обработка исключений в коде, когда это возможно, вместо использования неструктурированной обработки исключений и `On Error` и `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="808df-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="808df-119">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="808df-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="808df-120">Если вы используете `Resume` инструкции в любом отличный от в процедуру обработки ошибок, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="808df-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="808df-121">`Resume` Оператор не может использоваться в процедуре, содержащей `Try...Catch...Finally` инструкции.</span><span class="sxs-lookup"><span data-stu-id="808df-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="808df-122">Пример</span><span class="sxs-lookup"><span data-stu-id="808df-122">Example</span></span>  
 <span data-ttu-id="808df-123">В этом примере используется `Resume` инструкции для окончания обработки ошибки в процедуре, а затем возобновить выполнение с инструкцией, вызвавшей ошибку.</span><span class="sxs-lookup"><span data-stu-id="808df-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="808df-124">Чтобы проиллюстрировать использование создается ошибка номер 55 `Resume` инструкции.</span><span class="sxs-lookup"><span data-stu-id="808df-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="808df-125">Требования</span><span class="sxs-lookup"><span data-stu-id="808df-125">Requirements</span></span>  
 <span data-ttu-id="808df-126">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="808df-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="808df-127">**Сборка:** Visual Basic Runtime Library (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="808df-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="808df-128">См. также</span><span class="sxs-lookup"><span data-stu-id="808df-128">See Also</span></span>  
 [<span data-ttu-id="808df-129">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="808df-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="808df-130">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="808df-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="808df-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="808df-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
