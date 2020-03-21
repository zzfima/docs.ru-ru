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
# <a name="how-to-determine-the-active-mdi-child"></a>Практическое руководство. Определение активной дочерней MDI-формы
В некоторых случаях вы хотите предоставить команду, которая работает на элементе управления, который фокусируется на активной форме ребенка. Например, предположим, что вы хотите скопировать выбранный текст из текстового ящика детской формы на Clipboard. Можно создать процедуру, которая копирует выбранный текст <xref:System.Windows.Forms.Control.Click> в Clipboard, используя событие элемента меню Copy в стандартном меню Редактирования.  
  
 Поскольку приложение MDI может иметь много экземпляров одной и той же формы ребенка, процедура должна знать, какую форму использовать. Чтобы указать правильную <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> форму, используйте свойство, которое возвращает детскую форму, которая имеет фокус или которая была совсем недавно активной.  
  
 Если у вас есть несколько элементов управления на форме, вы также должны указать, какой элемент управления активен. Как <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> и имущество, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> имущество возвращает контроль с акцентом на активную форму ребенка. Ниже приведенная процедура иллюстрирует процедуру копирования, которую можно вызвать из меню детской формы, меню в форме MDI или кнопки панели инструментов.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Определить активный ребенок MDI (скопировать его текст в Clipboard)  
  
1. В рамках метода скопируйте текст активного управления активной детской формой в Clipboard.  
  
    > [!NOTE]
    > Этот пример предполагает, что есть родительская форма MDI (),`Form1`которая <xref:System.Windows.Forms.RichTextBox> имеет одно или несколько детских окон MDI, содержащих элемент управления. Для получения дополнительной информации [см.](how-to-create-mdi-parent-forms.md)  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Приложения с интерфейсом MDI](multiple-document-interface-mdi-applications.md)
- [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних MDI-форм](how-to-create-mdi-child-forms.md)
- [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](how-to-send-data-to-the-active-mdi-child.md)
- [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](how-to-arrange-mdi-child-forms.md)
