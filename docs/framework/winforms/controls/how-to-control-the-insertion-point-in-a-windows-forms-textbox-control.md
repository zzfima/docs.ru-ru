---
title: Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms
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
ms.openlocfilehash: 1fa6e8a3642086f81d0a62502d801ec6ade9b3d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110720"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="a5aef-102">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5aef-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="a5aef-103">Когда форм Windows <xref:System.Windows.Forms.TextBox> управления впервые получает фокус, по умолчанию курсор в текстовое поле находится слева от текста.</span><span class="sxs-lookup"><span data-stu-id="a5aef-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="a5aef-104">Пользователь может перемещать курсор с помощью мыши или клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="a5aef-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="a5aef-105">Если текстовое поле теряет и затем восстанавливает фокус, курсор будет везде, где пользователь последний раз поместил его.</span><span class="sxs-lookup"><span data-stu-id="a5aef-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="a5aef-106">В некоторых случаях такое поведение может быть всегда удобен для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5aef-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="a5aef-107">В текстовом редакторе приложение, пользователь может ожидать новые символы, который будет отображаться после любой существующий текст.</span><span class="sxs-lookup"><span data-stu-id="a5aef-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="a5aef-108">В приложение для ввода данных пользователь может ожидать новые символы для замены существующих записей.</span><span class="sxs-lookup"><span data-stu-id="a5aef-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="a5aef-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> И <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства позволяют изменить поведение в соответствии с вашими задачами.</span><span class="sxs-lookup"><span data-stu-id="a5aef-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="a5aef-110">Чтобы управление положением курсора в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a5aef-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="a5aef-111">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="a5aef-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="a5aef-112">Ноль помещает курсор непосредственно слева от первого символа.</span><span class="sxs-lookup"><span data-stu-id="a5aef-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="a5aef-113">(Необязательно) Задать <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> свойства длину текста, который вы хотите выбрать.</span><span class="sxs-lookup"><span data-stu-id="a5aef-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="a5aef-114">Приведенный ниже код всегда возвращает точку вставки на 0.</span><span class="sxs-lookup"><span data-stu-id="a5aef-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="a5aef-115">`TextBox1_Enter` Обработчик событий должен быть привязан к элементу управления; Дополнительные сведения, см. в разделе [Создание обработчиков событий в Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a5aef-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="a5aef-116">Как сделать курсор отображается по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a5aef-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="a5aef-117"><xref:System.Windows.Forms.TextBox> Курсор отображается по умолчанию в новой форме только если <xref:System.Windows.Forms.TextBox> элемент управления является первым в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="a5aef-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="a5aef-118">В противном случае курсор отображается только в том случае, если вы предоставите <xref:System.Windows.Forms.TextBox> фокус с клавиатуры или мыши.</span><span class="sxs-lookup"><span data-stu-id="a5aef-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="a5aef-119">Чтобы сделать видимым курсор по умолчанию на новую форму</span><span class="sxs-lookup"><span data-stu-id="a5aef-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="a5aef-120">Задайте <xref:System.Windows.Forms.TextBox> элемента управления <xref:System.Windows.Forms.Control.TabIndex%2A> свойства `0`.</span><span class="sxs-lookup"><span data-stu-id="a5aef-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5aef-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a5aef-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a5aef-122">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a5aef-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a5aef-123">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5aef-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a5aef-124">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="a5aef-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a5aef-125">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="a5aef-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a5aef-126">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5aef-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a5aef-127">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5aef-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a5aef-128">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="a5aef-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
