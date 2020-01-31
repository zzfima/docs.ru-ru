---
title: Управление точкой вставки в элементе управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742202"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="22891-102">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22891-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="22891-103">Когда элемент управления Windows Forms <xref:System.Windows.Forms.TextBox> сначала получает фокус, вставка по умолчанию в текстовое поле будет находиться слева от любого существующего текста.</span><span class="sxs-lookup"><span data-stu-id="22891-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="22891-104">Пользователь может переместить точку вставки с помощью клавиатуры или мыши.</span><span class="sxs-lookup"><span data-stu-id="22891-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="22891-105">Если текстовое поле теряется, а затем восстанавливает фокус, точка вставки будет находиться там, где пользователь последний раз поместил его.</span><span class="sxs-lookup"><span data-stu-id="22891-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="22891-106">В некоторых случаях такое поведение может быть неспособным относиться к пользователю.</span><span class="sxs-lookup"><span data-stu-id="22891-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="22891-107">В приложении для обработки текстов пользователь может ожидать, что новые символы будут отображаться после любого существующего текста.</span><span class="sxs-lookup"><span data-stu-id="22891-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="22891-108">В приложении ввода данных пользователь может ожидать, что новые символы будут заменены любой существующей записью.</span><span class="sxs-lookup"><span data-stu-id="22891-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="22891-109">Свойства <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> и <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> позволяют изменить поведение в соответствии с вашими целями.</span><span class="sxs-lookup"><span data-stu-id="22891-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="22891-110">Управление точкой вставки в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="22891-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="22891-111">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="22891-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="22891-112">Ноль помещает точку вставки непосредственно слева от первого символа.</span><span class="sxs-lookup"><span data-stu-id="22891-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="22891-113">Используемых Задайте для свойства <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> длину текста, который необходимо выбрать.</span><span class="sxs-lookup"><span data-stu-id="22891-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="22891-114">Приведенный ниже код всегда возвращает точку вставки в 0.</span><span class="sxs-lookup"><span data-stu-id="22891-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="22891-115">Обработчик событий `TextBox1_Enter` должен быть привязан к элементу управления; Дополнительные сведения см. [в разделе Создание обработчиков событий в Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="22891-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="22891-116">Как сделать точку вставки видимой по умолчанию</span><span class="sxs-lookup"><span data-stu-id="22891-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="22891-117">Точка вставки <xref:System.Windows.Forms.TextBox> по умолчанию отображается в новой форме только в том случае, если элемент управления <xref:System.Windows.Forms.TextBox> первым в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="22891-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="22891-118">В противном случае точка вставки появляется только в том случае, если вы передаете <xref:System.Windows.Forms.TextBox> фокусе с помощью клавиатуры или мыши.</span><span class="sxs-lookup"><span data-stu-id="22891-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="22891-119">Как сделать точку вставки текстового поля видимой по умолчанию в новой форме</span><span class="sxs-lookup"><span data-stu-id="22891-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="22891-120">Задайте для свойства <xref:System.Windows.Forms.Control.TabIndex%2A> элемента управления <xref:System.Windows.Forms.TextBox> значение `0`.</span><span class="sxs-lookup"><span data-stu-id="22891-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22891-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="22891-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="22891-122">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="22891-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="22891-123">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22891-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="22891-124">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="22891-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="22891-125">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="22891-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="22891-126">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22891-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="22891-127">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22891-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="22891-128">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="22891-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
