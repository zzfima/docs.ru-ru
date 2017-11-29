---
title: "Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms"
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
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: caf5cef9e23134715101545902e32e72d63c0aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms
Поле пароля — это текстовое поле Windows Forms, выводит заполнителем, когда пользователь вводит строку.  
  
### <a name="to-create-a-password-text-box"></a>Чтобы создать текстовое поле пароля  
  
1.  Задать <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства <xref:System.Windows.Forms.TextBox> элемента управления к определенному символу.  
  
     <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Свойство определяет знак, используемый в текстовом поле. К примеру, если вы хотите звездочки, отображается в поле "пароль", указать * для <xref:System.Windows.Forms.TextBox.PasswordChar%2A> в окне свойств. То какие бы знаки пользователь вводит в текстовое поле, отображается звездочка.  
  
2.  (Необязательно) Задать <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> свойства. Это свойство определяет, сколько символов можно ввести в текстовом поле. В случае превышения максимального система издает звуковой сигнал и текстовое поле не принимает любые дополнительные символы. Обратите внимание, что вы можете делать это в качестве максимальной длины пароля не может быть использована злоумышленниками, пытающимися подобрать пароль.  
  
     В следующем примере кода показано, как инициализировать текстовое поле, будет принимать строку до 14 символов и должны отображаться звездочки вместо строки. `InitializeMyControl` Процедура не выполняется автоматически; он должен быть вызван.  
  
    > [!IMPORTANT]
    >  С помощью <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойство текстового поля может помочь обеспечить пользователям не может определить пароль пользователя, наблюдая за его вводом. Эта мера безопасности не влияет на процесс сохранения или передачи пароля, может произойти из-за логики приложения. Поскольку введенный текст не зашифрован каким-либо образом, необходимо рассматривать его как и другие конфиденциальные данные. Несмотря на то, что он не отображается таким образом, пароль по-прежнему обрабатывается как обычный текст (если не реализовано дополнительные меры безопасности).  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TextBox>  
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
