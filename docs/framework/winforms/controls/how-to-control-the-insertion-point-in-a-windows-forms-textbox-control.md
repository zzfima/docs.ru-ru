---
title: Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms
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
ms.openlocfilehash: ced563eb063bbcc429cdf1447a0158459e5d5c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530742"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms
Если в Windows Forms <xref:System.Windows.Forms.TextBox> управления впервые получает фокус, по умолчанию курсор в текстовом поле слева от текста. Пользователь может перемещать курсор с помощью клавиатуры или мыши. Если текстовое поле теряет и затем восстанавливает фокус, курсор будет везде, где пользователь последний раз поместил его.  
  
 В некоторых случаях такое поведение может быть всегда удобен для пользователя. В текстовом редакторе приложение, пользователь может ожидать новые символы, который будет отображаться после существующий текст. В приложении ввода данных может ожидаться новые символы для замены существующих записей. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> И <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства позволяют изменить поведение в соответствии с конкретными требованиями.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Чтобы управлять положением курсора в элементе управления TextBox  
  
1.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> соответствующее значение. Ноль помещает курсор непосредственно слева от первого символа.  
  
2.  (Необязательно) Задать <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства длины текста, который вы хотите выбрать.  
  
     В следующем примере кода всегда возвращает точку вставки на 0. `TextBox1_Enter` Обработчик событий должен быть привязан к элементу управления; Дополнительные сведения см. в разделе [Создание обработчиков событий в Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Как сделать курсор отображается по умолчанию  
 <xref:System.Windows.Forms.TextBox> Курсор отображается по умолчанию в новой форме только если <xref:System.Windows.Forms.TextBox> элемент управления является первым в последовательности табуляции. В противном случае курсор будет отображаться только в том случае, если вы предоставляете <xref:System.Windows.Forms.TextBox> фокуса с помощью клавиатуры или мыши.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Чтобы сделать видимым курсор по умолчанию в новую форму  
  
-   Задать <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.Control.TabIndex%2A> свойства `0`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextBox>  
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
