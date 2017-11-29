---
title: "Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08ad19f3daca43fb33e845b632ac7d92b00f544c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms
Выделите текст программными средствами в Windows Forms <xref:System.Windows.Forms.TextBox> элемента управления. Например при создании функции, которая выполняет текст для определенной строки, можно выбрать текст для визуального уведомления положения найденной строки.  
  
### <a name="to-select-text-programmatically"></a>Выделение текста программными средствами  
  
1.  Задать <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> свойства в начало текста, который вы хотите выбрать.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Свойство является число, которое указывает курсор в текстовой строке, причем 0 крайней левой позиции. Если <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> свойству присвоено значение меньше, чем количество символов в текстовом поле, точка вставки помещается за последним знаком.  
  
2.  Задать <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства длины текста, который вы хотите выбрать.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Свойство является числовое значение, которое задает ширину курсора. Параметр <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> больше нуля, это количество выделяемых знаков, начиная с текущей позиции курсора.  
  
3.  (Необязательно) Доступ к выделенного текста до <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> свойство.  
  
     В следующем примере выделяется содержимое текстового поля при элемента управления <xref:System.Windows.Forms.Control.Enter> событием. В этом примере проверяется, если текстовое поле имеет значение для <xref:System.Windows.Forms.TextBox.Text%2A> свойство, не `null` или пустая строка. Когда текстовое поле получает фокус, выбран текущий текст в текстовом поле. `TextBox1_Enter` Обработчик событий должен быть привязан к элементу управления; Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Чтобы протестировать этот пример, нажимайте клавишу Tab фокус на текстовое поле. Если щелкнуть текстовое поле, текст не выбран.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextBox>  
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
