---
title: Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms
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
ms.openlocfilehash: 8fd1cfb0764d16b86cd639d8266d1cceff874932
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536698"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="70c3a-102">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70c3a-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="70c3a-103">Выделите текст программными средствами в Windows Forms <xref:System.Windows.Forms.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="70c3a-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="70c3a-104">Например при создании функции, которая выполняет текст для определенной строки, можно выбрать текст для визуального уведомления положения найденной строки.</span><span class="sxs-lookup"><span data-stu-id="70c3a-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="70c3a-105">Выделение текста программными средствами</span><span class="sxs-lookup"><span data-stu-id="70c3a-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="70c3a-106">Задать <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> свойства в начало текста, который вы хотите выбрать.</span><span class="sxs-lookup"><span data-stu-id="70c3a-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="70c3a-107"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> Свойство является число, которое указывает курсор в текстовой строке, причем 0 крайней левой позиции.</span><span class="sxs-lookup"><span data-stu-id="70c3a-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="70c3a-108">Если <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> свойству присвоено значение меньше, чем количество символов в текстовом поле, точка вставки помещается за последним знаком.</span><span class="sxs-lookup"><span data-stu-id="70c3a-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="70c3a-109">Задать <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства длины текста, который вы хотите выбрать.</span><span class="sxs-lookup"><span data-stu-id="70c3a-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="70c3a-110"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> Свойство является числовое значение, которое задает ширину курсора.</span><span class="sxs-lookup"><span data-stu-id="70c3a-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="70c3a-111">Параметр <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> больше нуля, это количество выделяемых знаков, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="70c3a-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="70c3a-112">(Необязательно) Доступ к выделенного текста до <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="70c3a-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="70c3a-113">В следующем примере выделяется содержимое текстового поля при элемента управления <xref:System.Windows.Forms.Control.Enter> событием.</span><span class="sxs-lookup"><span data-stu-id="70c3a-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="70c3a-114">В этом примере проверяется, если текстовое поле имеет значение для <xref:System.Windows.Forms.TextBox.Text%2A> свойство, не `null` или пустая строка.</span><span class="sxs-lookup"><span data-stu-id="70c3a-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="70c3a-115">Когда текстовое поле получает фокус, выбран текущий текст в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="70c3a-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="70c3a-116">`TextBox1_Enter` Обработчик событий должен быть привязан к элементу управления; Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="70c3a-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="70c3a-117">Чтобы протестировать этот пример, нажимайте клавишу Tab фокус на текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="70c3a-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="70c3a-118">Если щелкнуть текстовое поле, текст не выбран.</span><span class="sxs-lookup"><span data-stu-id="70c3a-118">If you click in the text box, the text is unselected.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70c3a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="70c3a-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="70c3a-120">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="70c3a-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="70c3a-121">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70c3a-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="70c3a-122">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70c3a-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="70c3a-123">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="70c3a-123">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="70c3a-124">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="70c3a-124">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="70c3a-125">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70c3a-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="70c3a-126">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="70c3a-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
