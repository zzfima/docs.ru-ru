---
title: Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: 56391777c75db288c33d1b2192355be0df50f7ee
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046121"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms

Поле пароля — это Windows Forms текстовое поле, которое отображает символы-заместители, когда пользователь вводит строку.

### <a name="to-create-a-password-text-box"></a>Создание текстового поля пароля

1. Задайте для <xref:System.Windows.Forms.TextBox> свойства элемента управления конкретный символ. <xref:System.Windows.Forms.TextBox.PasswordChar%2A>

    <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Свойство определяет символ, отображаемый в текстовом поле. Например, если вы хотите, чтобы в поле пароль отображались звездочки, укажите * для <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства в окно свойств. Затем, независимо от того, какой символ пользователь вводит в текстовое поле, отображается звездочка.

2. Используемых <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Задайте свойство. Свойство определяет, сколько символов можно ввести в текстовое поле. Если превышена максимальная длина, система выдает звуковой сигнал, и текстовое поле не принимает больше символов. Обратите внимание, что это может быть нежелательно, так как максимальная длина пароля может быть использована хакерами, пытающимися угадать пароль.

    В следующем примере кода показано, как инициализировать текстовое поле, которое будет принимать строку длиной до 14 символов и отображать звездочки вместо строки. `InitializeMyControl` Процедура не будет выполнена автоматически; ее необходимо вызвать.

    > [!IMPORTANT]
    > <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Использование свойства в текстовом поле позволяет гарантировать, что другие пользователи не смогут определить пароль пользователя, если он следит за его вводом. Эта мера безопасности не охватывает никаких операций хранения или передачи пароля, которые могут возникать из-за логики приложения. Поскольку введенный текст не шифруется каким-либо образом, его следует обрабатывать так же, как любые другие конфиденциальные данные. Несмотря на то, что он не отображается, пароль по-прежнему обрабатывается как обычный текст (если не была реализована дополнительная мера безопасности).

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

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление точкой вставки в элементе управления TextBox Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля, доступного только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Заключить кавычки в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Просмотр нескольких строк в элементе управления TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
