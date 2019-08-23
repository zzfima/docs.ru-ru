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
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946218"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="0b3ce-102">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="0b3ce-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="0b3ce-103">Иногда требуется указать команду, которая будет работать с элементом управления, который имеет фокус на текущей активной дочерней форме.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="0b3ce-104">Например, предположим, что нужно скопировать выбранный текст из текстового поля дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="0b3ce-105">Вы создадите процедуру, которая копирует выбранный текст в буфер обмена с помощью <xref:System.Windows.Forms.Control.Click> события пункта меню Копировать в стандартном меню "Правка".</span><span class="sxs-lookup"><span data-stu-id="0b3ce-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="0b3ce-106">Поскольку приложение MDI может иметь много экземпляров одной и той же дочерней формы, процедура должна иметь представление о том, какую форму использовать.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="0b3ce-107">Чтобы указать правильную форму, используйте <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, которое возвращает дочернюю форму, имеющую фокус или которая была недавно активна.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="0b3ce-108">Если в форме имеется несколько элементов управления, необходимо также указать, какой элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="0b3ce-109">Как и <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> свойство, свойство возвращает элемент управления с фокусом на активную дочернюю форму. <xref:System.Windows.Forms.Form.ActiveMdiChild%2A></span><span class="sxs-lookup"><span data-stu-id="0b3ce-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="0b3ce-110">Приведенная ниже процедура иллюстрирует процедуру копирования, которую можно вызвать из меню дочерней формы, меню в форме MDI или кнопки на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="0b3ce-111">Определение активной дочерней MDI-формы (для копирования ее текста в буфер обмена)</span><span class="sxs-lookup"><span data-stu-id="0b3ce-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="0b3ce-112">В методе скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0b3ce-113">В этом примере предполагается, что имеется родительская`Form1`форма MDI () с одним или несколькими дочерними <xref:System.Windows.Forms.RichTextBox> окнами MDI, содержащими элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0b3ce-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="0b3ce-114">Дополнительные сведения см. в разделе [Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0b3ce-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0b3ce-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0b3ce-115">See also</span></span>

- [<span data-ttu-id="0b3ce-116">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="0b3ce-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="0b3ce-117">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="0b3ce-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="0b3ce-118">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="0b3ce-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="0b3ce-119">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="0b3ce-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="0b3ce-120">Практическое руководство. Расположить дочерние формы MDI</span><span class="sxs-lookup"><span data-stu-id="0b3ce-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
