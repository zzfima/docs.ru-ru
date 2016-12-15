---
title: "Устранение неполадок, связанных с прослушивателями журнала (Visual Basic) | Microsoft Docs"
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
  - "журналы событий, устранение неполадок"
  - "устранение неполадок записи событий"
  - "устранение неполадок - Visual Basic, журналы событий"
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.  
  
 Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале.  Если фильтры настроены неправильно, журналы могут содержать неверные данные.  Дополнительные сведения о фильтрации см. в разделе [Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации.  Эту информацию можно получить с помощью многофункционального свойства журнала `TraceSource`.  
  
### Определение прослушивателей журнала для объекта Log в коде  
  
1.  Импортируйте пространство имен <xref:System.Diagnostics> в начале файла с кодом.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  Создайте функцию, возвращающую строку, состоящую из информации о каждом из прослушивателей журнала.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)