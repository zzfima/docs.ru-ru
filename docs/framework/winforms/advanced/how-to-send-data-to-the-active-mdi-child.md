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
ms.openlocfilehash: 0a7a2475891488d1fdd60f0db4a483c144a73f0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947846"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Практическое руководство. Отправка данных в активную дочернюю MDI-форму
Часто в контексте приложений с многодокументным [интерфейсом (MDI)](multiple-document-interface-mdi-applications.md)необходимо отправить данные в активное дочернее окно, например когда пользователь вставил данные из буфера обмена в приложение MDI.  
  
> [!NOTE]
> Сведения о проверке того, какое дочернее окно имеет фокус и отправляет свое содержимое в буфер обмена, см. в разделе [Определение активной дочерней MDI-формы](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Отправка данных в активное дочернее окно MDI из буфера обмена  
  
1. В методе скопируйте текст из буфера обмена в активный элемент управления активной дочерней формы.  
  
    > [!NOTE]
    > В этом примере предполагается, что имеется родительская`Form1`форма MDI () с одним или несколькими дочерними <xref:System.Windows.Forms.RichTextBox> окнами MDI, содержащими элемент управления. Дополнительные сведения см. в разделе [Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>См. также

- [Приложения с интерфейсом MDI](multiple-document-interface-mdi-applications.md)
- [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних форм MDI](how-to-create-mdi-child-forms.md)
- [Практическое руководство. Определение активной дочерней MDI-формы](how-to-determine-the-active-mdi-child.md)
- [Практическое руководство. Расположить дочерние формы MDI](how-to-arrange-mdi-child-forms.md)
