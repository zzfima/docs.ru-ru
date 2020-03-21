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
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Практическое руководство. Отправка данных в активную дочернюю MDI-форму
Часто в контексте [приложений с многопользовательским интерфейсом (MDI)](multiple-document-interface-mdi-applications.md)необходимо отправлять данные в активное окно дочернего ребенка, например, когда пользователь вставляет данные из Clipboard в приложение MDI.  
  
> [!NOTE]
> Для получения информации о проверке того, какое окно ребенка имеет фокус и отправки его содержимого в Clipboard, [см. Определение активного ребенка MDI](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Отправка данных в активное окно ребенка MDI из буфера обмена  
  
1. В рамках метода скопируйте текст на Clipboard для активного контроля активной детской формы.  
  
    > [!NOTE]
    > Этот пример предполагает, что есть родительская форма MDI (),`Form1`которая <xref:System.Windows.Forms.RichTextBox> имеет одно или несколько детских окон MDI, содержащих элемент управления. Для получения дополнительной информации [см.](how-to-create-mdi-parent-forms.md)  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Приложения с интерфейсом MDI](multiple-document-interface-mdi-applications.md)
- [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](how-to-create-mdi-child-forms.md)
- [Практическое руководство. Определение активной дочерней MDI-формы](how-to-determine-the-active-mdi-child.md)
- [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](how-to-arrange-mdi-child-forms.md)
