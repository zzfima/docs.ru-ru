---
title: Практическое руководство. Определение активной дочерней MDI-формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 81cb9b55f53c152e755ada1803e4ba5731498627
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229476"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="bad0d-102">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="bad0d-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="bad0d-103">В некоторых случаях требуется предоставить это команда, работающая на элементе управления, имеющий фокус на данный момент активной дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="bad0d-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="bad0d-104">Например предположим, что вы хотите копировать выделенный текст из текстового поля дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="bad0d-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="bad0d-105">Необходимо создать процедуру, которая копирует выделенный текст в буфер обмена с помощью <xref:System.Windows.Forms.Control.Click> событие копию элемента меню на стандартные меню "Правка".</span><span class="sxs-lookup"><span data-stu-id="bad0d-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="bad0d-106">Поскольку MDI-приложения можно создать несколько экземпляров того же дочерней формы, процедура должна знать, какую форму для использования.</span><span class="sxs-lookup"><span data-stu-id="bad0d-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="bad0d-107">Чтобы указать требуемую форму, используйте <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, которое возвращает, имеющий фокус, или это было самую последнюю активную дочернюю форму.</span><span class="sxs-lookup"><span data-stu-id="bad0d-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="bad0d-108">При наличии нескольких элементов управления в форме, необходимо также указать, какой элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="bad0d-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="bad0d-109">Как и <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> возвращает элемент управления с фокусом на активной дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="bad0d-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="bad0d-110">Следующая процедура служит примером процедуры копирования, которые могут вызываться из меню дочерней формы, из меню MDI-формы, или кнопку панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="bad0d-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="bad0d-111">Для определения активной дочерней MDI-формы (чтобы скопировать его текст в буфер обмена)</span><span class="sxs-lookup"><span data-stu-id="bad0d-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1.  <span data-ttu-id="bad0d-112">В методе скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="bad0d-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bad0d-113">В этом примере предполагается, имеется родительская форма MDI (`Form1`), имеет один или несколько дочерних MDI-окон содержащий <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bad0d-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="bad0d-114">Дополнительные сведения см. в разделе [Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bad0d-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bad0d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bad0d-115">See also</span></span>

- [<span data-ttu-id="bad0d-116">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="bad0d-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="bad0d-117">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="bad0d-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="bad0d-118">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="bad0d-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="bad0d-119">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="bad0d-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="bad0d-120">Практическое руководство. Упорядочение дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="bad0d-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
