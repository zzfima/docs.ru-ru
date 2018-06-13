---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 5e45f713a433365b4bbc8286154a3b877b08ec59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597879"
---
# <a name="resume-without-error"></a><span data-ttu-id="27a87-102">Выполнение оператора Resume без ошибки</span><span class="sxs-lookup"><span data-stu-id="27a87-102">Resume without error</span></span>
<span data-ttu-id="27a87-103">Объект `Resume` инструкции обнаружен вне кода обработки ошибок, или код выполнил переход в обработчик ошибок, даже если ошибок не было.</span><span class="sxs-lookup"><span data-stu-id="27a87-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="27a87-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="27a87-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="27a87-105">Переместить `Resume` инструкции в обработчик ошибок или удалите его.</span><span class="sxs-lookup"><span data-stu-id="27a87-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="27a87-106">Переход к меткам не может выполняться в рамках процедуры, поэтому следует выполнить поиск процедуры для метки, которая определяет обработчик ошибок.</span><span class="sxs-lookup"><span data-stu-id="27a87-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="27a87-107">Если обнаружена повторяющаяся метка, указанный в качестве целевого объекта `GoTo` инструкции, которые не `On Error GoTo` инструкции, измените метку строки, чтобы с его намеченной цели.</span><span class="sxs-lookup"><span data-stu-id="27a87-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a87-108">См. также</span><span class="sxs-lookup"><span data-stu-id="27a87-108">See Also</span></span>  
 [<span data-ttu-id="27a87-109">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="27a87-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="27a87-110">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="27a87-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
