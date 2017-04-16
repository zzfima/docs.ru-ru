---
title: "Практическое руководство. Отправка данных в активную дочернюю MDI-форму | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "дочерние формы"
  - "буфер обмена, возвращение данных"
  - "буфер обмена, вставка"
  - "MDI - интерфейс, передача данных формам"
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Отправка данных в активную дочернюю MDI-форму
Часто в контексте [приложений с многодокументным интерфейсом \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md) требуется отправить данные в активное дочернее окно. Например, это требуется в том случае, если пользователь вставляет данные из буфера обмена в приложение с MDI\-интерфейсом.  
  
> [!NOTE]
>  Сведения о том, как проверить, в каком дочернем окне находится фокус, и как отправить содержимое этого окна в буфер обмена, см. в разделе [Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### Чтобы отправить данные в активную дочернюю MDI\-форму из буфера обмена  
  
1.  В методе скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.  
  
    > [!NOTE]
    >  В этом примере предполагается, что существует родительская форма MDI \(`Form1`\), которая имеет одну или несколько дочерних MDI\-окон, содержащих элемент управления <xref:System.Windows.Forms.RichTextBox>.  Дополнительные сведения см. в разделе [Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
  
## См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Практическое руководство. Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)