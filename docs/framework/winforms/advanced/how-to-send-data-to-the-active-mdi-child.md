---
title: "Практическое руководство. Отправка данных в активную дочернюю MDI-форму"
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
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f505d68bfd6d8c65104244f9583fd3cf975dd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Практическое руководство. Отправка данных в активную дочернюю MDI-форму
Часто в контексте [приложений многодокументного интерфейса (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), вам потребуется отправить данные в активное дочернее окно, например когда пользователь вставляет данные из буфера обмена в MDI-приложения.  
  
> [!NOTE]
>  Сведения о проверке фокус какие дочернее окно и отправить содержимое в буфер обмена см. в разделе [определение активной дочерней MDI-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Для отправки данных в активную дочернюю MDI из буфера обмена  
  
1.  Внутри метода копировать текст в буфер обмена для активного элемента управления активной дочерней формы.  
  
    > [!NOTE]
    >  Этот пример предполагает, что имеется родительской формы MDI (`Form1`), имеет один или несколько дочерних MDI окон, содержащих <xref:System.Windows.Forms.RichTextBox> элемента управления. Дополнительные сведения см. в разделе [Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Практическое руководство. Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Практическое руководство. Создание дочерних MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Практическое руководство. Определение активной дочерней MDI-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
