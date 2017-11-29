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
ms.openlocfilehash: 3a4141a27a3b195dbb747a827d2bd9426a948f83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="92842-102">Практическое руководство. Добавление кавычек в строку (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="92842-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="92842-103">Бывает, что в строку текста нужно вставить кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="92842-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="92842-104">Например:</span><span class="sxs-lookup"><span data-stu-id="92842-104">For example:</span></span>  
  
 <span data-ttu-id="92842-105">Она сказала: "Ты этого заслуживаешь!"</span><span class="sxs-lookup"><span data-stu-id="92842-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="92842-106">В качестве альтернативы можно также использовать <xref:Microsoft.VisualBasic.ControlChars.Quote> качестве константы.</span><span class="sxs-lookup"><span data-stu-id="92842-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="92842-107">Вставка кавычек в строку в коде</span><span class="sxs-lookup"><span data-stu-id="92842-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="92842-108">В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] вставьте двойные кавычки в строку как внедренную кавычку.</span><span class="sxs-lookup"><span data-stu-id="92842-108">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="92842-109">В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] вставьте escape-последовательность \\" как внедренную кавычку.</span><span class="sxs-lookup"><span data-stu-id="92842-109">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="92842-110">Например, для создания представленной выше строки используйте следующий код.</span><span class="sxs-lookup"><span data-stu-id="92842-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="92842-111">-или-</span><span class="sxs-lookup"><span data-stu-id="92842-111">-or-</span></span>  
  
2.  <span data-ttu-id="92842-112">Вставьте для получения кавычки символ ASCII или Юникод.</span><span class="sxs-lookup"><span data-stu-id="92842-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="92842-113">В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] используйте символ ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="92842-113">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], use the ASCII character (34).</span></span> <span data-ttu-id="92842-114">В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] используйте символ Юникод (\u0022).</span><span class="sxs-lookup"><span data-stu-id="92842-114">In [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], use the Unicode character (\u0022).</span></span>  
  
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
    >  <span data-ttu-id="92842-115">В данном примере использовать \u0022 нельзя, поскольку нельзя использовать универсальное имя символа, обозначающее символ в базовом наборе символов.</span><span class="sxs-lookup"><span data-stu-id="92842-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="92842-116">В противном случае вы получите C3851.</span><span class="sxs-lookup"><span data-stu-id="92842-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="92842-117">Дополнительные сведения см. в разделе [Ошибка компилятора C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="92842-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="92842-118">-или-</span><span class="sxs-lookup"><span data-stu-id="92842-118">-or-</span></span>  
  
3.  <span data-ttu-id="92842-119">Также можно определить для символа константу и при необходимости использовать ее.</span><span class="sxs-lookup"><span data-stu-id="92842-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92842-120">См. также</span><span class="sxs-lookup"><span data-stu-id="92842-120">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [<span data-ttu-id="92842-121">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="92842-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="92842-122">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92842-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="92842-123">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92842-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="92842-124">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="92842-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="92842-125">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92842-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="92842-126">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92842-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="92842-127">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="92842-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
