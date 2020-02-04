---
title: Задание параметров с помощью элементов управления CheckBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746767"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms
Элемент управления <xref:System.Windows.Forms.CheckBox> Windows Forms используется для предоставления пользователям значения true/false или да/нет. При выборе элемента управления отображается галочка.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Задание параметров с помощью элементов управления CheckBox  
  
1. Проверьте значение свойства <xref:System.Windows.Forms.CheckBox.Checked%2A>, чтобы определить его состояние, и используйте это значение для установки параметра.  
  
     В приведенном ниже примере кода при возникновении события <xref:System.Windows.Forms.CheckBox.CheckedChanged> элемента управления <xref:System.Windows.Forms.CheckBox> свойство формы <xref:System.Windows.Forms.Control.AllowDrop%2A> устанавливается в значение `false`, если установлен флажок. Это полезно в ситуациях, когда требуется ограничить взаимодействие с пользователем.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Элемент управления CheckBox](checkbox-control-windows-forms.md)
