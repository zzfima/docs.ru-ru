---
title: Выбор текста в элементе управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745318"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms
Текст можно выбрать программным способом в элементе управления Windows Forms <xref:System.Windows.Forms.TextBox>. Например, при создании функции, выполняющей поиск определенной строки в тексте, можно выбрать текст, чтобы визуально предупредить читателя о положении найденной строки.  
  
### <a name="to-select-text-programmatically"></a>Выбор текста программным способом  
  
1. Задайте в качестве значения свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> начало текста, который необходимо выбрать.  
  
     Свойство <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> — это число, указывающее точку вставки в текстовой строке, а 0 — самое левое положение. Если для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> задано значение, которое больше числа символов в текстовом поле или превышает его, точка вставки помещается после последнего символа.  
  
2. Задайте для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> длину текста, который необходимо выбрать.  
  
     Свойство <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> — это числовое значение, которое задает ширину точки вставки. Установка для <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> числа больше 0 приводит к тому, что число символов будет выбрано, начиная с текущей точки вставки.  
  
3. Используемых Доступ к выбранному тексту осуществляется с помощью свойства <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>.  
  
     Приведенный ниже код выбирает содержимое текстового поля при возникновении события <xref:System.Windows.Forms.Control.Enter> элемента управления. В этом примере проверяется, имеет ли текстовое поле значение для свойства <xref:System.Windows.Forms.TextBox.Text%2A>, которое не `null` или является пустой строкой. Когда текстовое поле получает фокус, выделяется текущий текст в текстовом поле. Обработчик событий `TextBox1_Enter` должен быть привязан к элементу управления; Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Чтобы протестировать этот пример, нажимайте клавишу TAB, пока текстовое поле не найдет фокус. Если щелкнуть в текстовом поле, то текст не будет выбран.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
