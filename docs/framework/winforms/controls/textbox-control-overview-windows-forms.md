---
title: Общие сведения об элементе управления TextBox
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
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742803"
---
# <a name="textbox-control-overview-windows-forms"></a>Общие сведения об элементе управления TextBox (Windows Forms)
Windows Forms текстовые поля используются для получения входных данных от пользователя или для вывода текста. Элемент управления <xref:System.Windows.Forms.TextBox> обычно используется для редактируемого текста, хотя его также можно сделать доступным только для чтения. Текстовые поля могут отображать несколько строк, переносить текст в размер элемента управления и добавлять базовое форматирование. Элемент управления <xref:System.Windows.Forms.TextBox> предоставляет один стиль формата для текста, отображаемого или вводимых в элемент управления. Чтобы отобразить несколько типов форматированного текста, используйте элемент управления <xref:System.Windows.Forms.RichTextBox>. Дополнительные сведения см. в разделе [Общие сведения об элементе управления RichTextBox](richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Работа с элементом управления TextBox  
 Текст, отображаемый элементом управления, содержится в свойстве <xref:System.Windows.Forms.TextBox.Text%2A>. По умолчанию в текстовом поле можно ввести до 2048 символов. Если для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> задано значение `true`, можно ввести до 32 КБ текста. Свойство <xref:System.Windows.Forms.TextBox.Text%2A> может быть задано во время разработки с помощью окна Свойства, во время выполнения в коде или ввода пользователем во время выполнения. Текущее содержимое текстового поля можно получить во время выполнения, читая свойство <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
 В следующем примере кода во время выполнения задается текст в элементе управления. Процедура `InitializeMyControl` не будет выполняться автоматически; Он должен быть вызван.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.TextBox>
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
