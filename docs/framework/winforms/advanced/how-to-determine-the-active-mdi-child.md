---
title: "Практическое руководство. Определение активной дочерней MDI-формы"
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
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 473cf67f01db8735eb3b32a7549296f827e66ef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="90821-102">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="90821-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="90821-103">В некоторых случаях может потребоваться предоставить это команда, работающая на элементе управления, в котором фокус находится на активной дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="90821-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="90821-104">Например предположим, что вы хотите копировать выделенный текст из текстового поля дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="90821-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="90821-105">Необходимо создать процедуру, которая копирует выделенный текст в буфер обмена с помощью <xref:System.Windows.Forms.Control.Click> событие команды "Копировать" в стандартном меню Правка.</span><span class="sxs-lookup"><span data-stu-id="90821-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="90821-106">Поскольку MDI-приложения может быть несколько экземпляров той же дочерней формы, процедура должна знать, какую форму для использования.</span><span class="sxs-lookup"><span data-stu-id="90821-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="90821-107">Чтобы указать требуемую форму, используйте <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, которое возвращает дочернюю форму, которая находится в фокусе или использовалась последнюю активную.</span><span class="sxs-lookup"><span data-stu-id="90821-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="90821-108">При наличии нескольких элементов управления в форме, необходимо также указать, какой элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="90821-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="90821-109">Как <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> возвращает элемент управления с фокусом на активной дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="90821-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="90821-110">Следующая процедура служит примером процедуры копирования, которую можно вызвать из меню дочерней формы, из меню MDI-формы или кнопки панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="90821-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="90821-111">Чтобы определить активную дочернюю форму MDI (чтобы скопировать текст в буфер обмена)</span><span class="sxs-lookup"><span data-stu-id="90821-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1.  <span data-ttu-id="90821-112">Внутри метода скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="90821-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90821-113">Этот пример предполагает, что имеется родительской формы MDI (`Form1`), имеет один или несколько дочерних MDI окон, содержащих <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="90821-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="90821-114">Дополнительные сведения см. в разделе [Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="90821-114">For more information, see [Creating MDI Parent Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90821-115">См. также</span><span class="sxs-lookup"><span data-stu-id="90821-115">See Also</span></span>  
 [<span data-ttu-id="90821-116">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="90821-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="90821-117">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="90821-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="90821-118">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="90821-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="90821-119">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="90821-119">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="90821-120">Практическое руководство. Упорядочение дочерних форм интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="90821-120">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
