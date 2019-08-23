---
title: Практическое руководство. Заключить кавычки в строку (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 20828f75eeae9df33fcc22d8558b26a8a1ab2bdc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910423"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Практическое руководство. Заключить кавычки в строку (Windows Forms)
Бывает, что в строку текста нужно вставить кавычки (" "). Например:  
  
 Она сказала: "Ты этого заслуживаешь!"  
  
 В качестве альтернативы можно также использовать <xref:Microsoft.VisualBasic.ControlChars.Quote> поле как константу.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>Вставка кавычек в строку в коде  
  
1. В Visual Basic вставьте две кавычки в строку в качестве внедренной кавычки. В визуальных C# и C++визуальных элементах вставьте \\escape-последовательность "как внедренную кавычку. Например, для создания представленной выше строки используйте следующий код.  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     -или-  
  
2. Вставьте для получения кавычки символ ASCII или Юникод. В Visual Basic используйте символ ASCII (34). В визуальном C#элементе используйте символ Юникода (\u0022).  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > В данном примере использовать \u0022 нельзя, поскольку нельзя использовать универсальное имя символа, обозначающее символ в базовом наборе символов. В противном случае вы получите C3851. Дополнительные сведения см. в разделе [Ошибка компилятора C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     -или-  
  
3. Также можно определить для символа константу и при необходимости использовать ее.  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление точкой вставки в элементе управления TextBox Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля, доступного только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Просмотр нескольких строк в элементе управления TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
