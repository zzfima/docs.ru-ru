---
title: "Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms | Microsoft Docs"
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
  - "положение курсора, Элементы управления TextBox"
  - "текстовые поля, управление положением курсора"
  - "TextBox - элемент управления [Windows Forms], положение курсора"
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms
Когда элемент управления Windows Forms <xref:System.Windows.Forms.TextBox> впервые получает фокус, по умолчанию курсор устанавливается слева от текста, если он содержится в текстовом поле.  Пользователь может изменять положение курсора с помощью клавиатуры или мыши.  Если элемент управления теряет фокус и затем получает его снова, курсор будет установлен в том положении, куда пользователь последний раз поместил его.  
  
 Такой режим не всегда удобен для пользователя.  Например, в текстовом редакторе пользователь может ожидать появления новых знаков после имеющегося текста.  В приложении ввода данных может ожидаться замена существующих записей новыми знаками.  Свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> и <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> позволяют изменять положение курсора в соответствии с конкретными требованиями.  
  
### Чтобы управлять положением курсора в элементе управления TextBox  
  
1.  Присвойте соответствующее значение свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>.  Нуль означает, что курсор помещается слева от первого знака.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> значение, равное длине текста, который требуется выделить \(необязательное действие\).  
  
     Приведенный ниже код всегда возвращает точку вставки в нулевое положение.  Обработчик событий `TextBox1_Enter` должен быть связан с элементом управления; дополнительные сведения см. в разделе [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## Как сделать курсор видимым по умолчанию  
 Курсор <xref:System.Windows.Forms.TextBox> является по умолчанию видимым в новой форме только если элемент управления <xref:System.Windows.Forms.TextBox> является первым в порядке табуляции.  В противном случае курсор будет отображаться только если передать элементу <xref:System.Windows.Forms.TextBox> фокус с помощью мыши или клавиатуры.  
  
#### Чтобы сделать курсор видимым по умолчанию в новой форме  
  
-   Присвойте свойству <xref:System.Windows.Forms.Control.TabIndex%2A> элемента управления <xref:System.Windows.Forms.TextBox> значение `0`.  
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)