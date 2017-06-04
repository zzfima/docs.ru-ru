---
title: "Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms | Microsoft Docs"
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
  - "поля для ввода паролей, создание"
  - "PasswordChar - свойство (текстовые поля)"
  - "пароли, маска ввода"
  - "пароли, текстовое поле для ввода пароля"
  - "TextBox - элемент управления [Windows Forms], ввод пароля"
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms
Поле пароля — это текстовое поле Windows Forms, в котором вместо вводимой пользователем строки текста отображаются знаки\-заполнители.  
  
### Создание текстового поля для ввода пароля  
  
1.  Установите для свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> элемента управления <xref:System.Windows.Forms.TextBox> определенный знак.  
  
     Свойство <xref:System.Windows.Forms.TextBox.PasswordChar%2A> определяет знак, используемый в текстовом поле.  Например, чтобы в поле пароля отображались звездочки, следует задать знак \* в качестве значения свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> в окне "Свойства".\<\].  После этого, какие бы знаки пользователь ни вводил в текстовом поле, вместо них будут отображаться звездочки.  
  
2.  \(Не обязательно\) Установите свойство <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>.  Это свойство определяет, сколько знаков может быть введено в текстовом поле.  При превышении максимального количества раздается звуковой сигнал и ввод других знаков в текстовое поле становится невозможным.  Задавать это свойство не всегда целесообразно, так как максимальная длина пароля может быть использована злоумышленниками, пытающимися подобрать пароль.  
  
     В следующем примере кода инициализируется текстовое поле, предназначенное для ввода строк длиной до 14 знаков, вместо которых должны отображаться звездочки.  Процедура`InitializeMyControl` не выполняется автоматически; она должна быть вызвана.  
  
    > [!IMPORTANT]
    >  Использование свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> для текстового поля позволяет скрыть пароль от других лиц, присутствующих при вводе пароля пользователем.  Однако данная мера не влияет на процесс сохранения или передачи пароля, выполняемый в соответствии с логикой приложения.  Поскольку вводимый текст никак не шифруется, с ним следует обращаться так же, как с другими конфиденциальными данными.  Пароль, несмотря на измененное представление в текстовом поле, фактически остается строкой обычного текста \(если не были предусмотрены дополнительные меры безопасности\).  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)