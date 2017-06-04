---
title: "Общие сведения об элементе управления TextBox (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "текстовые поля, добавление"
  - "TextBox - элемент управления [Windows Forms], сведения об элементах управления TextBox"
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления TextBox (Windows Forms)
Текстовые поля форм Windows Forms используются для приема данных, вводимых пользователем, или для отображения текста.  Элемент управления <xref:System.Windows.Forms.TextBox> обычно используется для редактируемого текста, хотя его можно также сделать доступным только для чтения.  В текстовых полях можно выводить несколько строк текста, размещать текст в соответствии с размером элемента управления и применять основные элементы форматирования.  В элементе управления <xref:System.Windows.Forms.TextBox> можно вводить или отображать текст только в одном формате.  Для отображения текста в различных форматах следует использовать элемент управления <xref:System.Windows.Forms.RichTextBox>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## Работа с элементом управления TextBox  
 Текст, отображаемый в элементе управления, содержится в свойстве <xref:System.Windows.Forms.TextBox.Text%2A>.  По умолчанию в текстовом поле можно ввести до 2048 знаков.  Если свойству <xref:System.Windows.Forms.TextBox.Multiline%2A> присвоить значение `true`, это позволит вводить до 32 килобайт текста.  Свойство <xref:System.Windows.Forms.TextBox.Text%2A> может быть установлено в окне "Свойства" во время разработки, программными средствами во время выполнения или в результате ввода данных пользователем во время выполнения.  Текущее содержимое текстового поля может быть получено во время выполнения путем считывания значения свойства <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
 В следующем примере кода текст помещается в элемент управления во время выполнения.  Процедура`InitializeMyControl` не выполняется автоматически; она должна быть вызвана.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)