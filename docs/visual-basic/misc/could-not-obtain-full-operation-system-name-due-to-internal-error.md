---
title: "Не удалось получить полное имя операционной системы из-за внутренней ошибки"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65796c41d2a9fbd03517e7b15bc6b566ba4364fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="8c587-102">Не удалось получить полное имя операционной системы из-за внутренней ошибки</span><span class="sxs-lookup"><span data-stu-id="8c587-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="8c587-103">Не удалось получить полное имя операционной системы из-за внутренней ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c587-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="8c587-104">Это может быть вызвано отсутствием WMI на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="8c587-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="8c587-105">Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="8c587-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="8c587-106">Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="8c587-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c587-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8c587-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="8c587-108">Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="8c587-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="8c587-109">Дополнительные сведения об инструментарии WMI и для ее установки перейдите к и поиск «Основы инструментария управления Windows».</span><span class="sxs-lookup"><span data-stu-id="8c587-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c587-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8c587-110">See Also</span></span>  
 [<span data-ttu-id="8c587-111">Свойство My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="8c587-111">My.Computer.Info.OSFullName Property</span></span>](http://msdn.microsoft.com/en-us/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)  
 [<span data-ttu-id="8c587-112">Исключения и обработка ошибок в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c587-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="8c587-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="8c587-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
