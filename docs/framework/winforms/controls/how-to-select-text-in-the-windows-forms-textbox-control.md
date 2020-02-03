---
title: Выбор текста в элементе управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745318"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="b7a26-102">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a26-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="b7a26-103">Текст можно выбрать программным способом в элементе управления Windows Forms <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b7a26-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="b7a26-104">Например, при создании функции, выполняющей поиск определенной строки в тексте, можно выбрать текст, чтобы визуально предупредить читателя о положении найденной строки.</span><span class="sxs-lookup"><span data-stu-id="b7a26-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="b7a26-105">Выбор текста программным способом</span><span class="sxs-lookup"><span data-stu-id="b7a26-105">To select text programmatically</span></span>  
  
1. <span data-ttu-id="b7a26-106">Задайте в качестве значения свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> начало текста, который необходимо выбрать.</span><span class="sxs-lookup"><span data-stu-id="b7a26-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="b7a26-107">Свойство <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> — это число, указывающее точку вставки в текстовой строке, а 0 — самое левое положение.</span><span class="sxs-lookup"><span data-stu-id="b7a26-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="b7a26-108">Если для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> задано значение, которое больше числа символов в текстовом поле или превышает его, точка вставки помещается после последнего символа.</span><span class="sxs-lookup"><span data-stu-id="b7a26-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="b7a26-109">Задайте для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> длину текста, который необходимо выбрать.</span><span class="sxs-lookup"><span data-stu-id="b7a26-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="b7a26-110">Свойство <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> — это числовое значение, которое задает ширину точки вставки.</span><span class="sxs-lookup"><span data-stu-id="b7a26-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="b7a26-111">Установка для <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> числа больше 0 приводит к тому, что число символов будет выбрано, начиная с текущей точки вставки.</span><span class="sxs-lookup"><span data-stu-id="b7a26-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="b7a26-112">Используемых Доступ к выбранному тексту осуществляется с помощью свойства <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7a26-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="b7a26-113">Приведенный ниже код выбирает содержимое текстового поля при возникновении события <xref:System.Windows.Forms.Control.Enter> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b7a26-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="b7a26-114">В этом примере проверяется, имеет ли текстовое поле значение для свойства <xref:System.Windows.Forms.TextBox.Text%2A>, которое не `null` или является пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="b7a26-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="b7a26-115">Когда текстовое поле получает фокус, выделяется текущий текст в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="b7a26-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="b7a26-116">Обработчик событий `TextBox1_Enter` должен быть привязан к элементу управления; Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b7a26-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="b7a26-117">Чтобы протестировать этот пример, нажимайте клавишу TAB, пока текстовое поле не найдет фокус.</span><span class="sxs-lookup"><span data-stu-id="b7a26-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="b7a26-118">Если щелкнуть в текстовом поле, то текст не будет выбран.</span><span class="sxs-lookup"><span data-stu-id="b7a26-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b7a26-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7a26-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="b7a26-120">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="b7a26-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b7a26-121">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a26-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="b7a26-122">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a26-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b7a26-123">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="b7a26-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="b7a26-124">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="b7a26-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="b7a26-125">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a26-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b7a26-126">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="b7a26-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
