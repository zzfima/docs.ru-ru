---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: ecbed5b59d36b1984c0b0ae161821ea99d28e090
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334644"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="9b824-102">Не удалось получить полное имя операционной системы из-за внутренней ошибки</span><span class="sxs-lookup"><span data-stu-id="9b824-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="9b824-103">Не удалось получить полное имя операционной системы из-за внутренней ошибки.</span><span class="sxs-lookup"><span data-stu-id="9b824-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="9b824-104">Это может быть вызвано отсутствием WMI на текущем компьютере.</span><span class="sxs-lookup"><span data-stu-id="9b824-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="9b824-105">Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="9b824-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="9b824-106">Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="9b824-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b824-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9b824-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9b824-108">Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="9b824-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="9b824-109">Дополнительные сведения о WMI и его установке перейдите и искать «Основы инструментария управления Windows».</span><span class="sxs-lookup"><span data-stu-id="9b824-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b824-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9b824-110">See also</span></span>

- [<span data-ttu-id="9b824-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="9b824-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="9b824-112">Обработка и создание исключений в .NET</span><span class="sxs-lookup"><span data-stu-id="9b824-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="9b824-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="9b824-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
