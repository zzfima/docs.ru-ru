---
title: Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
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
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914984"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox> <xref:System.Windows.Forms.Control.Click> , возникает событие. Приложение можно запрограммировать для выполнения некоторых действий в зависимости от состояния флажка.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Реагирование на нажатия кнопки CheckBox  
  
1. В обработчике <xref:System.Windows.Forms.CheckBox.Checked%2A>событийиспользуйте свойство для определения состояния элемента управления и выполнения необходимых действий. <xref:System.Windows.Forms.Control.Click>  
  
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
    > Если пользователь пытается дважды щелкнуть <xref:System.Windows.Forms.CheckBox> элемент управления, каждый щелчок будет обрабатываться отдельно, то есть <xref:System.Windows.Forms.CheckBox> элемент управления не поддерживает событие двойного щелчка.  
  
    > [!NOTE]
    > Если свойство имеет `true` значение (по умолчанию), <xref:System.Windows.Forms.CheckBox> то при щелчке автоматически выбирается или удаляется. <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> В противном случае необходимо вручную задать <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство <xref:System.Windows.Forms.Control.Click> при возникновении события.  
  
     Можно также использовать <xref:System.Windows.Forms.CheckBox> элемент управления для определения курса действий.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Определение курса действий при нажатии на флажок  
  
1. Используйте оператор Case для запроса значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойства, чтобы определить направление действия. Если свойство имеет `true`значение, <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство может возвращать три возможных значения, которые представляют проверяемую рамку, флажок снят или третье неопределенное состояние, при котором поле отображается серым цветом. <xref:System.Windows.Forms.CheckBox.ThreeState%2A> внешний вид, указывающий, что параметр недоступен.  
  
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
    > `true` <xref:System.Windows.Forms.CheckBox.Checked%2A> `true` Если свойство имеет значение, свойство возвращается для<xref:System.Windows.Forms.CheckState.Checked> и .<xref:System.Windows.Forms.CheckState.Indeterminate> <xref:System.Windows.Forms.CheckBox.ThreeState%2A>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Настройка параметров с помощью элементов управления CheckBox Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Элемент управления CheckBox](checkbox-control-windows-forms.md)
