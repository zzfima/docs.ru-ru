---
title: "How to: Connect Multiple Events to a Single Event Handler in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "events [Windows Forms], connecting multiple to single event handler"
  - "event handlers [Windows Forms], connecting events to"
  - "menus, event-handling methods for multiple menu items"
  - "Windows Forms controls, events"
  - "menu items, multicasting event-handling methods"
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Connect Multiple Events to a Single Event Handler in Windows Forms
При разработке приложения может оказаться необходимым наличие одного обработчика событий, используемого для нескольких событий, или одной процедуры, запускаемой несколькими событиями.  Например, большая экономия времени часто достигается благодаря тому, что команда меню и кнопка формы, имеющие одинаковое функциональное назначение, активизируют одно и то же событие.  Этого можно достичь с помощью представления событий окна свойств в C\# или используя зарезервированное слово `Handles` и раскрывающиеся поля **Имя класса** и **Имя метода** в редакторе кода Visual Basic.  
  
### Чтобы связать несколько событий с одним обработчиком событий в Visual Basic, выполните следующие действия.  
  
1.  Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.  
  
2.  В раскрывающемся поле **Имя класса** выделите один из элементов управления, для которого необходима обработка обработчика событий.  
  
3.  В раскрывающемся поле **Имя метода** выделите одно из событий, для которого необходима обработка обработчика событий.  
  
4.  В редакторе кода производится вставка соответствующего обработчика событий и определяется положение курсора внутри метода.  В приведенном ниже примере это событие <xref:System.Windows.Forms.Control.Click> для элемента управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Добавьте другие события, которые необходимо обработать, в предложение `Handles` .  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Добавьте соответствующий код в обработчик событий.  
  
### Чтобы подключить несколько событий к одному обработчику событий в C\#, выполните следующие действия.  
  
1.  Выделите элемент управления, к которому необходимо подключить обработчик событий.  
  
2.  В окне "Свойства" нажмите кнопку **События** \(![Кнопка событий](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton\_PropertiesWindow")\).  
  
3.  Щелкните имя события, которое необходимо обработать.  
  
4.  В разделе значений рядом с именем события нажмите кнопку раскрывающегося списка для отображения списка существующих обработчиков событий, соответствующих сигнатуре метода события, которое необходимо обработать.  
  
5.  Выделите в списке подходящий обработчик событий.  
  
     Чтобы связать событие с существующим обработчиком событий, код будет добавлен в форму.  
  
## См. также  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)