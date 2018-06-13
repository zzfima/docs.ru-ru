---
title: Общие сведения об элементе управления TextBox (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: b15de762b166fb66ff926706e93cbac6d0c6ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539871"
---
# <a name="textbox-control-overview-windows-forms"></a>Общие сведения об элементе управления TextBox (Windows Forms)
Windows Forms текстовые поля используются для получения входных данных от пользователя или для отображения текста. <xref:System.Windows.Forms.TextBox> Управления обычно используется для редактируемого текста, хотя его можно также сделать доступным только для чтения. Текстовые поля можно отобразить несколько строк, переноса текста по размеру элемента управления и добавлять основные элементы форматирования. <xref:System.Windows.Forms.TextBox> Элемент управления предоставляет единый формат стиля или ввести в элемент управления отображать текст. Чтобы отобразить несколько типов форматированного текста, используйте <xref:System.Windows.Forms.RichTextBox> элемента управления. Дополнительные сведения см. в разделе [Обзор элемента управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Работа с элементом управления TextBox  
 Текст, отображаемый элементом управления, содержащихся в <xref:System.Windows.Forms.TextBox.Text%2A> свойство. По умолчанию можно ввести не более 2048 символов в текстовом поле. Если задать <xref:System.Windows.Forms.TextBox.Multiline%2A> свойства `true`, можно ввести текст до 32 КБ. <xref:System.Windows.Forms.TextBox.Text%2A> Свойство можно задать во время разработки в окне "Свойства" во время выполнения в коде, или вводимыми пользователем во время выполнения. Текущее содержимое текстового поля могут быть получены во время выполнения путем чтения <xref:System.Windows.Forms.TextBox.Text%2A> свойство.  
  
 В следующем примере кода задает текст в элементе управления во время выполнения. `InitializeMyControl` Процедура не выполняется автоматически; он должен быть вызван.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextBox>  
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
