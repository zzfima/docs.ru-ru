---
title: "Невозможно произвести запись в файл журнала, так как это приведет к превышению значения MaximumSize."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4d284f9e1a79e409a41aed57ec880fc371b8332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>Невозможно произвести запись в файл журнала, так как это приведет к превышению значения MaximumSize.
Класс <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> не может выполнить запись в файл журнала, так как:  
  
-   размер файла журнала (в байтах) больше, чем значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>   
  
     и  
  
-   значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> равно <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.  
  
2.  Измените значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> , чтобы разрешить журналы больших размеров.  
  
3.  Задайте для свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> значение <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> , чтобы отменить сообщения без предупреждения, если журнал окажется слишком большим.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [Объект My.Application.Log](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [Объект My.Log](../../visual-basic/language-reference/objects/my-log-object.md)
