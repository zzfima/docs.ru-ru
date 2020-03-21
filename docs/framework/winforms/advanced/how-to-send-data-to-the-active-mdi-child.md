---
title: Практическое руководство. Отправка данных в активную дочернюю MDI-форму
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182498"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="e9340-102">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="e9340-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="e9340-103">Часто в контексте [приложений с многопользовательским интерфейсом (MDI)](multiple-document-interface-mdi-applications.md)необходимо отправлять данные в активное окно дочернего ребенка, например, когда пользователь вставляет данные из Clipboard в приложение MDI.</span><span class="sxs-lookup"><span data-stu-id="e9340-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9340-104">Для получения информации о проверке того, какое окно ребенка имеет фокус и отправки его содержимого в Clipboard, [см. Определение активного ребенка MDI](how-to-determine-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="e9340-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="e9340-105">Отправка данных в активное окно ребенка MDI из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="e9340-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="e9340-106">В рамках метода скопируйте текст на Clipboard для активного контроля активной детской формы.</span><span class="sxs-lookup"><span data-stu-id="e9340-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e9340-107">Этот пример предполагает, что есть родительская форма MDI (),`Form1`которая <xref:System.Windows.Forms.RichTextBox> имеет одно или несколько детских окон MDI, содержащих элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e9340-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="e9340-108">Для получения дополнительной информации [см.](how-to-create-mdi-parent-forms.md)</span><span class="sxs-lookup"><span data-stu-id="e9340-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();
                }  
             }  
          }  
          catch
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e9340-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9340-109">See also</span></span>

- [<span data-ttu-id="e9340-110">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="e9340-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="e9340-111">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="e9340-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="e9340-112">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="e9340-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="e9340-113">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="e9340-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="e9340-114">Практическое руководство. Упорядочение дочерних форм интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="e9340-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
