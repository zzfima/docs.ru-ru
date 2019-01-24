---
title: Невозможно получить поток для журнала
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 0553da64ca8fcac148cd8da5c22227b5824387de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628751"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Невозможно получить поток для журнала
Невозможно получить поток для журнала. Потенциальные имена файлов, на основе \<имя > уже используются.  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> Класс не удалось создать новый файл журнала, так как все возможные имена файлов журнала на основе \<имя > уже используются.  
  
 Наличие слишком большого количества файлов журнала может быть признаком проблем с архитектурой приложения. Дополнительные сведения содержатся в документации по классу <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Установите свойство <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> в значение <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> или <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> , чтобы включить метку даты в имя файла журнала.  
  
2.  Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
