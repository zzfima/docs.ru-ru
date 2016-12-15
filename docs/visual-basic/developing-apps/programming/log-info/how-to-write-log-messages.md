---
title: "Практическое руководство. Запись сообщений в журнал (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Объект My.Application.Log, запись сообщений журнала"
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Запись сообщений в журнал (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Для записи в журнал информации о приложении можно использовать объекты `My.Application.Log` и `My.Log`. В этом примере показано использование метода `My.Application.Log.WriteEntry` для записи в журнал данных трассировки.  
  
 Для записи в журнал информации об исключениях используйте метод `My.Application.Log.WriteException`; см. раздел [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
## Пример  
 В этом примере используется метод `My.Application.Log.WriteEntry` для записи данных трассировки.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## Безопасность платформы .NET Framework  
 Убедитесь в том, что записываемые в журнал данные не включают конфиденциальных сведений, например паролей пользователей. Дополнительные сведения см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Пошаговое руководство. Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)