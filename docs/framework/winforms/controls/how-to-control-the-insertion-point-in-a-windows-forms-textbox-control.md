---
title: Управление точкой вставки в элементе управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742202"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms
Когда элемент управления Windows Forms <xref:System.Windows.Forms.TextBox> сначала получает фокус, вставка по умолчанию в текстовое поле будет находиться слева от любого существующего текста. Пользователь может переместить точку вставки с помощью клавиатуры или мыши. Если текстовое поле теряется, а затем восстанавливает фокус, точка вставки будет находиться там, где пользователь последний раз поместил его.  
  
 В некоторых случаях такое поведение может быть неспособным относиться к пользователю. В приложении для обработки текстов пользователь может ожидать, что новые символы будут отображаться после любого существующего текста. В приложении ввода данных пользователь может ожидать, что новые символы будут заменены любой существующей записью. Свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> и <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> позволяют изменить поведение в соответствии с вашими целями.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Управление точкой вставки в элементе управления TextBox  
  
1. Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> соответствующее значение. Ноль помещает точку вставки непосредственно слева от первого символа.  
  
2. Используемых Задайте для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> длину текста, который необходимо выбрать.  
  
     Приведенный ниже код всегда возвращает точку вставки в 0. Обработчик событий `TextBox1_Enter` должен быть привязан к элементу управления; Дополнительные сведения см. [в разделе Создание обработчиков событий в Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Как сделать точку вставки видимой по умолчанию  
 Точка вставки <xref:System.Windows.Forms.TextBox> по умолчанию отображается в новой форме только в том случае, если элемент управления <xref:System.Windows.Forms.TextBox> первым в последовательности табуляции. В противном случае точка вставки появляется только в том случае, если вы передаете <xref:System.Windows.Forms.TextBox> фокусе с помощью клавиатуры или мыши.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Как сделать точку вставки текстового поля видимой по умолчанию в новой форме  
  
- Задайте для свойства <xref:System.Windows.Forms.Control.TabIndex%2A> элемента управления <xref:System.Windows.Forms.TextBox> значение `0`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
