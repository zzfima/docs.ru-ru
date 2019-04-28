---
title: Невозможно получить поток для журнала
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 540ff3fbba72d33b2efaa58ad7a8019628f5e83f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922542"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="7411f-102">Невозможно получить поток для журнала</span><span class="sxs-lookup"><span data-stu-id="7411f-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="7411f-103">Невозможно получить поток для журнала.</span><span class="sxs-lookup"><span data-stu-id="7411f-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="7411f-104">Потенциальные имена файлов, на основе \<имя > уже используются.</span><span class="sxs-lookup"><span data-stu-id="7411f-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="7411f-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Класс не удалось создать новый файл журнала, так как все возможные имена файлов журнала на основе \<имя > уже используются.</span><span class="sxs-lookup"><span data-stu-id="7411f-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="7411f-106">Наличие слишком большого количества файлов журнала может быть признаком проблем с архитектурой приложения.</span><span class="sxs-lookup"><span data-stu-id="7411f-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="7411f-107">Дополнительные сведения содержатся в документации по классу <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="7411f-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7411f-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7411f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="7411f-109">Установите свойство <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> в значение <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> или <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> , чтобы включить метку даты в имя файла журнала.</span><span class="sxs-lookup"><span data-stu-id="7411f-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="7411f-110">Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.</span><span class="sxs-lookup"><span data-stu-id="7411f-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7411f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7411f-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="7411f-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="7411f-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="7411f-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="7411f-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
