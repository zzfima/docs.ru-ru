---
title: "Практическое руководство. Добавление кавычек в строку (Windows Forms)"
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
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 267a69b9470040dfc60f3c0b280b71e3f52dbc88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Практическое руководство. Добавление кавычек в строку (Windows Forms)
Бывает, что в строку текста нужно вставить кавычки (" "). Пример:  
  
 Она сказала: "Ты этого заслуживаешь!"  
  
 В качестве альтернативы можно также использовать <xref:Microsoft.VisualBasic.ControlChars.Quote> качестве константы.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>Вставка кавычек в строку в коде  
  
1.  В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] вставьте двойные кавычки в строку как внедренную кавычку. В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] вставьте escape-последовательность \\" как внедренную кавычку. Например, для создания представленной выше строки используйте следующий код.  
  
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
  
     - или -  
  
2.  Вставьте для получения кавычки символ ASCII или Юникод. В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] используйте символ ASCII (34). В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] используйте символ Юникод (\u0022).  
  
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
    >  В данном примере использовать \u0022 нельзя, поскольку нельзя использовать универсальное имя символа, обозначающее символ в базовом наборе символов. В противном случае вы получите C3851. Дополнительные сведения см. в разделе [Ошибка компилятора C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     - или -  
  
3.  Также можно определить для символа константу и при необходимости использовать ее.  
  
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
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
