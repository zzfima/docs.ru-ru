---
title: "Практическое руководство. Определение активной дочерней MDI-формы | Microsoft Docs"
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
  - "буфер обмена, копирование данных"
  - "MDI - интерфейс, активация форм"
  - "MDI - интерфейс, дочерние окна"
  - "MDI - интерфейс, поиск фокуса"
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Определение активной дочерней MDI-формы
В некоторых случаях требуется иметь команду, которая бы работала с элементом управления, находящимся в фокусе в текущей активной дочерней форме.  Предположим, что требуется скопировать выделенный текст из текстового поля дочерней формы в буфер обмена.  Необходимо создать процедуру, которая копирует выделенный текст в буфер обмена, используя событие <xref:System.Windows.Forms.Control.Click> команды "Копировать" в стандартном меню "Правка".  
  
 Так как в приложении с MDI\-интерфейсом могут существовать несколько экземпляров одной и той же дочерней формы, процедура должна знать, какую форму использовать.  Чтобы указать требуемую форму, используйте свойство <xref:System.Windows.Forms.Form.ActiveMdiChild%2A>, которое возвращает дочернюю форму, которая находится в фокусе или использовалась самой последней.  
  
 Если в форме существуют несколько элементов управления, требуется также указать активный элемент.  Подобно свойству <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> возвращает элемент управления с фокусом на активной дочерней форме.  Следующая процедура служит примером процедуры копирования, которую можно вызвать из меню дочерней формы, из меню формы с MDI\-интерфейсом или с помощью кнопки в панели инструментов.  
  
### Чтобы определить активную дочернюю MDI\-форму \(и скопировать ее текст в буфер обмена\)  
  
1.  В методе скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.  
  
    > [!NOTE]
    >  В этом примере предполагается, что существует родительская форма MDI \(`Form1`\), которая имеет одну или несколько дочерних MDI\-окон, содержащих элемент управления <xref:System.Windows.Forms.RichTextBox>.  Дополнительные сведения см. в разделе [Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
  
## См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Практическое руководство. Отправка данных в активную дочернюю MDI\-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)