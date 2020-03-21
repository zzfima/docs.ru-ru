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
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141852"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms
Элемент управления <xref:System.Windows.Forms.CheckBox> Windows Forms используется для предоставления пользователям true/False или Да/Нет опций. Элемент управления отображает контрольную отметку при выборе.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Установить параметры с помощью элементов управления CheckBox  
  
1. Изучите значение <xref:System.Windows.Forms.CheckBox.Checked%2A> свойства, чтобы определить его состояние, и используйте это значение для установки опции.  
  
     В приведенном ниже примере кода <xref:System.Windows.Forms.CheckBox.CheckedChanged> при поднятии события <xref:System.Windows.Forms.Control.AllowDrop%2A> <xref:System.Windows.Forms.CheckBox> элемента `false` управления свойство формы устанавливается в случае проверки флажка. Это полезно для ситуаций, когда требуется ограничить взаимодействие с пользователем.  
  
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
- [Контроль checkBox](checkbox-control-windows-forms.md)
