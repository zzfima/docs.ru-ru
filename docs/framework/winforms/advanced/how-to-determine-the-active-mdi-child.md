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
# <a name="how-to-determine-the-active-mdi-child"></a>Практическое руководство. Определение активной дочерней MDI-формы
Иногда требуется указать команду, которая будет работать с элементом управления, который имеет фокус на текущей активной дочерней форме. Например, предположим, что нужно скопировать выбранный текст из текстового поля дочерней формы в буфер обмена. Вы создадите процедуру, которая копирует выбранный текст в буфер обмена с помощью <xref:System.Windows.Forms.Control.Click> события пункта меню Копировать в стандартном меню "Правка".  
  
 Поскольку приложение MDI может иметь много экземпляров одной и той же дочерней формы, процедура должна иметь представление о том, какую форму использовать. Чтобы указать правильную форму, используйте <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> свойство, которое возвращает дочернюю форму, имеющую фокус или которая была недавно активна.  
  
 Если в форме имеется несколько элементов управления, необходимо также указать, какой элемент управления является активным. Как и <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> свойство, свойство возвращает элемент управления с фокусом на активную дочернюю форму. <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> Приведенная ниже процедура иллюстрирует процедуру копирования, которую можно вызвать из меню дочерней формы, меню в форме MDI или кнопки на панели инструментов.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Определение активной дочерней MDI-формы (для копирования ее текста в буфер обмена)  
  
1. В методе скопируйте текст активного элемента управления активной дочерней формы в буфер обмена.  
  
    > [!NOTE]
    > В этом примере предполагается, что имеется родительская`Form1`форма MDI () с одним или несколькими дочерними <xref:System.Windows.Forms.RichTextBox> окнами MDI, содержащими элемент управления. Дополнительные сведения см. в разделе [Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md).  
  
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

- [Приложения с интерфейсом MDI](multiple-document-interface-mdi-applications.md)
- [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Создание дочерних форм MDI](how-to-create-mdi-child-forms.md)
- [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](how-to-send-data-to-the-active-mdi-child.md)
- [Практическое руководство. Расположить дочерние формы MDI](how-to-arrange-mdi-child-forms.md)
