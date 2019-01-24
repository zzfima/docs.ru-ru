---
title: Как выполнить Настройка параметров с помощью элементов управления Windows Forms CheckBox
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
ms.openlocfilehash: a8159e9e9a2484b95399aba67b1a10b1252a4357
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525564"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Как выполнить Настройка параметров с помощью элементов управления Windows Forms CheckBox
Windows Forms <xref:System.Windows.Forms.CheckBox> элемент управления используется для предоставления пользователям True/False или Да/нет параметров. Элемент управления отображает флажок, когда он выбран.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Настройка параметров с помощью элементов управления CheckBox  
  
1.  Проверьте значение <xref:System.Windows.Forms.CheckBox.Checked%2A> свойства для определения его состояния и использовать его для задания параметра.  
  
     В примере кода ниже, когда <xref:System.Windows.Forms.CheckBox> элемента управления <xref:System.Windows.Forms.CheckBox.CheckedChanged> события формы <xref:System.Windows.Forms.Control.AllowDrop%2A> свойству `false` Если флажок установлен. Это полезно в ситуациях, где вы хотите ограничить взаимодействие с пользователем.  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Обработка события в Windows Forms щелчка элемента управления CheckBox](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)
- [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
