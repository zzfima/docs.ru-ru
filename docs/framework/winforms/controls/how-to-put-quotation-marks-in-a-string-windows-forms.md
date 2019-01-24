---
title: Как выполнить Добавление кавычек в строку (Windows Forms)
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
ms.openlocfilehash: 24d7ea17384a912fda454bfb1136696ab18d9843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651647"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="545e1-102">Как выполнить Добавление кавычек в строку (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="545e1-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="545e1-103">Бывает, что в строку текста нужно вставить кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="545e1-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="545e1-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="545e1-104">For example:</span></span>  
  
 <span data-ttu-id="545e1-105">Она сказала: "Ты этого заслуживаешь!"</span><span class="sxs-lookup"><span data-stu-id="545e1-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="545e1-106">Кроме того, можно также использовать <xref:Microsoft.VisualBasic.ControlChars.Quote> качестве константы.</span><span class="sxs-lookup"><span data-stu-id="545e1-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="545e1-107">Вставка кавычек в строку в коде</span><span class="sxs-lookup"><span data-stu-id="545e1-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="545e1-108">В Visual Basic вставьте двойные кавычки в строку как внедренную кавычку.</span><span class="sxs-lookup"><span data-stu-id="545e1-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="545e1-109">В визуальном элементе C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], вставьте escape-последовательность \\«как внедренную кавычку.</span><span class="sxs-lookup"><span data-stu-id="545e1-109">In Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="545e1-110">Например, для создания представленной выше строки используйте следующий код.</span><span class="sxs-lookup"><span data-stu-id="545e1-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="545e1-111">- или -</span><span class="sxs-lookup"><span data-stu-id="545e1-111">-or-</span></span>  
  
2.  <span data-ttu-id="545e1-112">Вставьте для получения кавычки символ ASCII или Юникод.</span><span class="sxs-lookup"><span data-stu-id="545e1-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="545e1-113">В Visual Basic используйте символ ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="545e1-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="545e1-114">В визуальном элементе C#, используйте символ Юникод (\u0022).</span><span class="sxs-lookup"><span data-stu-id="545e1-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    >  <span data-ttu-id="545e1-115">В данном примере использовать \u0022 нельзя, поскольку нельзя использовать универсальное имя символа, обозначающее символ в базовом наборе символов.</span><span class="sxs-lookup"><span data-stu-id="545e1-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="545e1-116">В противном случае вы получите C3851.</span><span class="sxs-lookup"><span data-stu-id="545e1-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="545e1-117">Дополнительные сведения см. в разделе [Ошибка компилятора C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="545e1-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="545e1-118">- или -</span><span class="sxs-lookup"><span data-stu-id="545e1-118">-or-</span></span>  
  
3.  <span data-ttu-id="545e1-119">Также можно определить для символа константу и при необходимости использовать ее.</span><span class="sxs-lookup"><span data-stu-id="545e1-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="545e1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="545e1-120">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="545e1-121">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="545e1-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="545e1-122">Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="545e1-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="545e1-123">Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545e1-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="545e1-124">Практическое руководство. Создать только для чтения текстовое поле</span><span class="sxs-lookup"><span data-stu-id="545e1-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="545e1-125">Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="545e1-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="545e1-126">Практическое руководство. Просмотр нескольких строк в элементе управления Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="545e1-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="545e1-127">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="545e1-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
