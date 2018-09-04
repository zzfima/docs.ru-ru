---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 192033348a779591a54860505d5d707a802c415a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560903"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="0e19b-102">Не удалось получить полное имя операционной системы из-за внутренней ошибки</span><span class="sxs-lookup"><span data-stu-id="0e19b-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="0e19b-103">Не удалось получить полное имя операционной системы из-за внутренней ошибки.</span><span class="sxs-lookup"><span data-stu-id="0e19b-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="0e19b-104">Это может быть вызвано отсутствием WMI на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="0e19b-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="0e19b-105">Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="0e19b-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="0e19b-106">Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="0e19b-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0e19b-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0e19b-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="0e19b-108">Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="0e19b-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="0e19b-109">Дополнительные сведения о WMI и его установке перейдите и искать «Основы инструментария управления Windows».</span><span class="sxs-lookup"><span data-stu-id="0e19b-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e19b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0e19b-110">See Also</span></span>  
 [<span data-ttu-id="0e19b-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="0e19b-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [<span data-ttu-id="0e19b-112">Исключения и обработка ошибок в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e19b-112">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="0e19b-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="0e19b-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
