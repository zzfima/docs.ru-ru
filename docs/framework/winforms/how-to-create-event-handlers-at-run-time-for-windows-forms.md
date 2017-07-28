---
title: "How to: Create Event Handlers at Run Time for Windows Forms | Microsoft Docs"
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
  - "Windows Forms, event handling"
  - "event handlers, creating"
  - "run time, creating event handlers at"
  - "examples [Windows Forms], event handling"
  - "Button control [Windows Forms], event handlers"
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Create Event Handlers at Run Time for Windows Forms
Помимо создания событий с помощью конструктора Windows Forms, можно также создать обработчик событий во время выполнения.  Это позволяет подключать обработчики событий не при запуске программы, а в зависимости от условий, возникающих в коде во время выполнения.  
  
### Чтобы создать обработчик событий во время выполнения, выполните следующие действия.  
  
1.  Откройте форму, к которой требуется добавить обработчик событий, в редакторе кода.  
  
2.  Добавьте в форму метод с сигнатурой для события, которое необходимо обработать.  
  
     Например, для обработки события <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> создайте метод, как показано ниже.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  Добавьте в обработчик событий код, соответствующий приложению.  
  
4.  Определите, для какой формы или элемента управления требуется создать обработчик событий.  
  
5.  Для метода в классе формы добавьте код, который определяет обработчик событий для обработки события.  Например, в следующем фрагменте кода определен обработчик событий `button1_Click`, который служит для обработки события <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Метод <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>, представленный в примере кода Visual Basic, создает обработчик событий нажатия кнопки.  
  
## См. также  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)   
 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)