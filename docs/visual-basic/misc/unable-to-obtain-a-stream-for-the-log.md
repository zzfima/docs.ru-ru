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
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Невозможно получить поток для журнала
Невозможно получить поток для журнала. Потенциальные имена файлов на основе \<имя > уже используются.  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Класса не удалось создать новый файл журнала, так как все возможные имена файлов журнала на основе \<имя > уже используются.  
  
 Наличие слишком большого количества файлов журнала может быть признаком проблем с архитектурой приложения. Дополнительные сведения содержатся в документации по классу <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Установите свойство <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> в значение <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> или <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> , чтобы включить метку даты в имя файла журнала.  
  
2.  Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [Объект My.Application.Log](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [Объект My.Log](../../visual-basic/language-reference/objects/my-log-object.md)
