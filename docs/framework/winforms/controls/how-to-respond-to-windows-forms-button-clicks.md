---
title: "Практическое руководство. Обработка события нажатия кнопки в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Button - элемент управления [Windows Forms], реакция на щелчок"
  - "кнопки, отклик на события Click"
  - "Click - событие, Button - элемент управления"
  - "Click - событие, реакция на"
  - "двойной щелчок"
  - "события [Windows Forms], события Click"
  - "примеры [Windows Forms], элементы управления"
  - "MouseDown - событие"
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Обработка события нажатия кнопки в Windows Forms
Чаще всего элемент управления <xref:System.Windows.Forms.Button> в Windows Forms используется для выполнения какой\-либо программы при нажатии кнопки.  
  
 Щелчок элемента управления <xref:System.Windows.Forms.Button> вызывает также некоторые другие события, например <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp>.  Если требуется вложить обработчики событий для таких событий, связанных с основным, убедитесь, что их действия не конфликтуют.  Например, если нажатие кнопки удаляет сведения, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должна появляться подсказка с несуществующими сведениями.  
  
 Если дважды щелкнуть элемент управления <xref:System.Windows.Forms.Button>, каждый щелчок будет обрабатываться отдельно; другими словами, этот элемент управления не поддерживает событие двойного щелчка.  
  
### Ответ на нажатие кнопки  
  
-   В обработчике`Click` <xref:System.EventHandler> кнопки напишите выполняемый код.  `Button1_Click` необходимо привязать к элементу управления.  Дополнительные сведения см. в разделе [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp#  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## См. также  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)