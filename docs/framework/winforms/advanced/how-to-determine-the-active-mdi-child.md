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
ms.workload: dotnet
ms.openlocfilehash: c026df631c2ac033594ea86887bb8440a6aa240a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-active-mdi-child"></a>Практическое руководство. Определение активной дочерней MDI-формы
В некоторых случаях может потребоваться предоставить это команда, работающая на элементе управления, в котором фокус находится на активной дочерней формы. Например предположим, что вы хотите копировать выделенный текст из текстового поля дочерней формы в буфер обмена. Необходимо создать процедуру, которая копирует выделенный текст в буфер обмена с помощью <xref:System.Windows.Forms.Control.Click> событие команды "Копировать" в стандартном меню Правка.  
  
 Поскольку MDI-приложения может быть несколько экземпляров той же дочерней формы, процедура должна знать, какую форму для использования. Чтобы указать требуемую форму, используйте <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, которое возвращает дочернюю форму, которая находится в фокусе или использовалась последнюю активную.  
  
 При наличии нескольких элементов управления в форме, необходимо также указать, какой элемент управления является активным. Как <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> возвращает элемент управления с фокусом на активной дочерней формы. Следующая процедура служит примером процедуры копирования, которую можно вызвать из меню дочерней формы, из меню MDI-формы или кнопки панели инструментов.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Чтобы определить активную дочернюю форму MDI (чтобы скопировать текст в буфер обмена)  
  
1.  Внутри метода скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.  
  
    > [!NOTE]
    >  Этот пример предполагает, что имеется родительской формы MDI (`Form1`), имеет один или несколько дочерних MDI окон, содержащих <xref:System.Windows.Forms.RichTextBox> элемента управления. Дополнительные сведения см. в разделе [Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Практическое руководство. Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Практическое руководство. Создание дочерних MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
