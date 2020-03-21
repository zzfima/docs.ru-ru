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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182548"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="64d2f-102">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="64d2f-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="64d2f-103">В некоторых случаях вы хотите предоставить команду, которая работает на элементе управления, который фокусируется на активной форме ребенка.</span><span class="sxs-lookup"><span data-stu-id="64d2f-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="64d2f-104">Например, предположим, что вы хотите скопировать выбранный текст из текстового ящика детской формы на Clipboard.</span><span class="sxs-lookup"><span data-stu-id="64d2f-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="64d2f-105">Можно создать процедуру, которая копирует выбранный текст <xref:System.Windows.Forms.Control.Click> в Clipboard, используя событие элемента меню Copy в стандартном меню Редактирования.</span><span class="sxs-lookup"><span data-stu-id="64d2f-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="64d2f-106">Поскольку приложение MDI может иметь много экземпляров одной и той же формы ребенка, процедура должна знать, какую форму использовать.</span><span class="sxs-lookup"><span data-stu-id="64d2f-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="64d2f-107">Чтобы указать правильную <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> форму, используйте свойство, которое возвращает детскую форму, которая имеет фокус или которая была совсем недавно активной.</span><span class="sxs-lookup"><span data-stu-id="64d2f-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="64d2f-108">Если у вас есть несколько элементов управления на форме, вы также должны указать, какой элемент управления активен.</span><span class="sxs-lookup"><span data-stu-id="64d2f-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="64d2f-109">Как <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> и имущество, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> имущество возвращает контроль с акцентом на активную форму ребенка.</span><span class="sxs-lookup"><span data-stu-id="64d2f-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="64d2f-110">Ниже приведенная процедура иллюстрирует процедуру копирования, которую можно вызвать из меню детской формы, меню в форме MDI или кнопки панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="64d2f-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="64d2f-111">Определить активный ребенок MDI (скопировать его текст в Clipboard)</span><span class="sxs-lookup"><span data-stu-id="64d2f-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="64d2f-112">В рамках метода скопируйте текст активного управления активной детской формой в Clipboard.</span><span class="sxs-lookup"><span data-stu-id="64d2f-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="64d2f-113">Этот пример предполагает, что есть родительская форма MDI (),`Form1`которая <xref:System.Windows.Forms.RichTextBox> имеет одно или несколько детских окон MDI, содержащих элемент управления.</span><span class="sxs-lookup"><span data-stu-id="64d2f-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="64d2f-114">Для получения дополнительной информации [см.](how-to-create-mdi-parent-forms.md)</span><span class="sxs-lookup"><span data-stu-id="64d2f-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64d2f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64d2f-115">See also</span></span>

- [<span data-ttu-id="64d2f-116">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="64d2f-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="64d2f-117">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="64d2f-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="64d2f-118">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="64d2f-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="64d2f-119">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="64d2f-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="64d2f-120">Практическое руководство. Упорядочение дочерних форм интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="64d2f-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
