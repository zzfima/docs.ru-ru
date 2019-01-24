---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 55295997e5e534b091063815d5ad1a37b81638ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686625"
---
# <a name="resume-without-error"></a><span data-ttu-id="06d59-102">Выполнение оператора Resume без ошибки</span><span class="sxs-lookup"><span data-stu-id="06d59-102">Resume without error</span></span>
<span data-ttu-id="06d59-103">Объект `Resume` инструкции обнаружен вне кода обработки ошибок, или код выполнил переход в обработчик ошибок, несмотря на то, что ошибок не было.</span><span class="sxs-lookup"><span data-stu-id="06d59-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06d59-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="06d59-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="06d59-105">Переместить `Resume` инструкции в обработчик ошибок или удалите его.</span><span class="sxs-lookup"><span data-stu-id="06d59-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="06d59-106">Переход к меткам не может выполняться в рамках процедуры, выполните поиск процедура метку, идентифицирующую обработчика ошибок.</span><span class="sxs-lookup"><span data-stu-id="06d59-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="06d59-107">Если вы нашли повторяющуюся метку, указанный в качестве целевого объекта `GoTo` инструкцию, которая не `On Error GoTo` инструкции, измените метку строки, чтобы с его намеченной цели.</span><span class="sxs-lookup"><span data-stu-id="06d59-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d59-108">См. также</span><span class="sxs-lookup"><span data-stu-id="06d59-108">See also</span></span>
- [<span data-ttu-id="06d59-109">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="06d59-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="06d59-110">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="06d59-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
