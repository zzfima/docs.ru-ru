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
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141930"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Всякий раз, когда пользователь <xref:System.Windows.Forms.CheckBox> нажимает на элемент управления Windows Forms, <xref:System.Windows.Forms.Control.Click> происходит событие. Вы можете запрограммировать приложение для выполнения некоторых действий в зависимости от состояния флажка.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Ответы на клики CheckBox  
  
1. В <xref:System.Windows.Forms.Control.Click> обработчике <xref:System.Windows.Forms.CheckBox.Checked%2A> событий используйте свойство для определения состояния элемента управления и выполняйте все необходимые действия.  
  
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
    > Если пользователь пытается дважды нажать <xref:System.Windows.Forms.CheckBox> на элемент управления, каждый клик будет обрабатываться отдельно; то есть <xref:System.Windows.Forms.CheckBox> элемент управления не поддерживает событие с двойным щелчком мыши.  
  
    > [!NOTE]
    > Когда <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> свойство `true` (по умолчанию), автоматически <xref:System.Windows.Forms.CheckBox> выбирается или очищается при нажатии. В противном случае необходимо <xref:System.Windows.Forms.CheckBox.Checked%2A> вручную <xref:System.Windows.Forms.Control.Click> настроить свойство при возникновении события.  
  
     Вы также можете <xref:System.Windows.Forms.CheckBox> использовать элемент управления для определения курса действий.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Определить курс действий при нажатии флажка  
  
1. Используйте выписку по случаю случая <xref:System.Windows.Forms.CheckBox.CheckState%2A> для запроса стоимости свойства для определения хода действий. Когда <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойство настроено `true` <xref:System.Windows.Forms.CheckBox.CheckState%2A> на, свойство может вернуть три возможных значения, которые представляют собой окно проверяется, окно не проверяется, или третье неопределенное состояние, в котором окно отображается с затемненным видом, чтобы указать опцию недоступна.  
  
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
    > Когда <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имущество `true`установлено, <xref:System.Windows.Forms.CheckBox.Checked%2A> имущество `true` возвращается <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate>для обоих и .  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Контроль checkBox](checkbox-control-windows-forms.md)
