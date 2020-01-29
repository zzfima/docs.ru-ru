---
title: Реагирование на нажатия флажков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735661"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox>, возникает событие <xref:System.Windows.Forms.Control.Click>. Приложение можно запрограммировать для выполнения некоторых действий в зависимости от состояния флажка.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Реагирование на нажатия кнопки CheckBox  
  
1. В обработчике событий <xref:System.Windows.Forms.Control.Click> используйте свойство <xref:System.Windows.Forms.CheckBox.Checked%2A>, чтобы определить состояние элемента управления и выполнить все необходимые действия.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Если пользователь пытается дважды щелкнуть элемент управления <xref:System.Windows.Forms.CheckBox>, каждый щелчок будет обрабатываться отдельно. то есть элемент управления <xref:System.Windows.Forms.CheckBox> не поддерживает событие двойного щелчка.  
  
    > [!NOTE]
    > Если свойство <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> `true` (по умолчанию), <xref:System.Windows.Forms.CheckBox> автоматически выбирается или удаляется при щелчке. В противном случае необходимо вручную задать свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> при возникновении события <xref:System.Windows.Forms.Control.Click>.  
  
     Для определения курса действий можно также использовать элемент управления <xref:System.Windows.Forms.CheckBox>.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Определение курса действий при нажатии на флажок  
  
1. Используйте оператор Case для запроса значения свойства <xref:System.Windows.Forms.CheckBox.CheckState%2A>, чтобы определить направление действия. Если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, то свойство <xref:System.Windows.Forms.CheckBox.CheckState%2A> может возвращать три возможных значения, которые представляют собой проверяемую рамку, флажок снят или третье неопределенное состояние, при котором окно отображается серым цветом, чтобы указать, что параметр недоступен.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` для <xref:System.Windows.Forms.CheckState.Checked> и <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Элемент управления CheckBox](checkbox-control-windows-forms.md)
