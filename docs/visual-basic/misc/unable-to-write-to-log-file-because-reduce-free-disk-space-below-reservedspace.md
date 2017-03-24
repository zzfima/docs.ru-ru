---
title: "Невозможно произвести запись в файл журнала, так как свободного места на диске останется меньше значения ReservedSpace | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrApplicationLog_ReservedSpaceEncroached"
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Невозможно произвести запись в файл журнала, так как свободного места на диске останется меньше значения ReservedSpace
Класс <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> не может выполнить запись в файл журнала, так как:  
  
-   объем свободного места на диске \(в байтах\) меньше, чем значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>  
  
     и  
  
-   значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> равно <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption>.  
  
### Исправление ошибки  
  
1.  Архивируйте существующие журналы и удалите их с компьютера, чтобы разрешить объекту <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> создавать новые журналы.  
  
2.  Измените значение свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> на меньшее число, чтобы зарезервировать меньше места на диске.  
  
3.  Задайте для свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> значение <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption> для отмены сообщений без предупреждения при нехватке свободного места на диске.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>   
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>   
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>   
 [Объект My.Application.Log](../../visual-basic/language-reference/objects/my-application-log-object.md)   
 [Объект My.Log](../../visual-basic/language-reference/objects/my-log-object.md)