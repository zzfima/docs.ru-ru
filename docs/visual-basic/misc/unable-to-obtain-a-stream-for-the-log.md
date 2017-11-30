---
title: "Невозможно получить поток для журнала"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd3051b2331502c9f4f3430bbf88731b307d1b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="40b9a-102">Невозможно получить поток для журнала</span><span class="sxs-lookup"><span data-stu-id="40b9a-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="40b9a-103">Невозможно получить поток для журнала.</span><span class="sxs-lookup"><span data-stu-id="40b9a-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="40b9a-104">Потенциальные имена файлов на основе \<имя > уже используются.</span><span class="sxs-lookup"><span data-stu-id="40b9a-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="40b9a-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Класса не удалось создать новый файл журнала, так как все возможные имена файлов журнала на основе \<имя > уже используются.</span><span class="sxs-lookup"><span data-stu-id="40b9a-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="40b9a-106">Наличие слишком большого количества файлов журнала может быть признаком проблем с архитектурой приложения.</span><span class="sxs-lookup"><span data-stu-id="40b9a-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="40b9a-107">Дополнительные сведения содержатся в документации по классу <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="40b9a-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40b9a-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="40b9a-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="40b9a-109">Установите свойство <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> в значение <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> или <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> , чтобы включить метку даты в имя файла журнала.</span><span class="sxs-lookup"><span data-stu-id="40b9a-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="40b9a-110">Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.</span><span class="sxs-lookup"><span data-stu-id="40b9a-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b9a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="40b9a-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="40b9a-112">Объект My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="40b9a-112">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="40b9a-113">Объект My.Log</span><span class="sxs-lookup"><span data-stu-id="40b9a-113">My.Log Object</span></span>](../../visual-basic/language-reference/objects/my-log-object.md)
