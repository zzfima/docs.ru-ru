---
title: "Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms | Microsoft Docs"
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
  - "текстовые поля, выделение текста программными средствами"
  - "текст, выделения текста в текстовых полях программными средствами"
  - "TextBox - элемент управления [Windows Forms], выделение текста программными средствами"
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms
В элементе управления Windows Forms <xref:System.Windows.Forms.TextBox> можно выделять текст программным способом.  Например, если создается функция, просматривающая текст в поисках определенной строки, то можно выделять текст для визуального уведомления о местоположении найденной строки.  
  
### Выделение текста программными средствами  
  
1.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> значение, соответствующее начальной позиции текста, который требуется выделить.  
  
     Значением свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> является число, определяющее положение курсора в текстовой строке, причем 0 указывает крайнюю левую позицию.  Если значение свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> больше или равно числу знаков в текстовом поле, то курсор помещается за последним знаком.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> значение, равное длине текста, который требуется выделить.  
  
     Значением свойства <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> является число, определяющее количество выделяемых знаков.  Если значение <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> больше нуля, то выделяется указанное количество знаков, начиная с текущей позиции курсора.  
  
3.  Воспользуйтесь свойством <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> для доступа к выделенному тексту.  
  
     В следующем примере выделяется содержимое текстового поля при обработке события <xref:System.Windows.Forms.Control.Enter> элемента управления.  В этом примере проверяется, имеется ли в текстовом поле значение свойства <xref:System.Windows.Forms.TextBox.Text%2A>, которое не является `null` или пустой строкой.  Когда фокус перемещается на текстовое поле, текущий текст в поле выделяется.  Обработчик событий `TextBox1_Enter` должен быть связан с элементом управления; дополнительные сведения см. в разделе [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Чтобы протестировать этот пример, нажимайте клавишу TAB, пока фокус не переместится на данное текстовое поле.  Если щелкнуть внутри текстового поля, выделение текста будет снято.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)