---
title: "Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "журналы событий, завершение работы"
  - "объект My.Application.Log, ведение журналов"
  - "Startup - событие"
  - "журналы событий, запуск"
  - "Shutdown - событие"
  - "объект My.Log, ведение журналов"
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении. В этом примере показан способ использования метода `My.Application.Log.WriteEntry` с событиями `Startup` и `Shutdown` для записи сведений трассировки.  
  
### Доступ к коду обработчика событий приложения  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  Перейдите на вкладку **Приложение**.  
  
3.  Нажмите кнопку **Просмотреть события приложения**, чтобы открыть редактор кода.  
  
     Откроется файл ApplicationEvents.vb.  
  
### Запись сообщений в журнал при запуске приложения  
  
1.  Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
2.  В меню **Объявления** выберите пункт **Запуск**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> до запуска главного приложения.  
  
3.  Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Startup`.  
  
     [!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]  
  
### Запись сообщений в журнал при завершении работы приложения  
  
1.  Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
2.  В меню **Объявления** выберите пункт **Завершение работы**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> после запуска основного приложения, но до завершения его работы.  
  
3.  Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Shutdown`.  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## Пример  
 Для доступа к событиям приложения в редакторе кода можно использовать **конструктор проектов**. Дополнительные сведения см. в разделе [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)