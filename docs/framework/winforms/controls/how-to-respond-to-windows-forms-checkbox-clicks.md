---
title: "Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms"
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
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f15adb84f92c9434d6835e80f08bf1d9bd500ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Каждый раз, когда пользователь нажимает кнопку Windows Forms <xref:System.Windows.Forms.CheckBox> управления <xref:System.Windows.Forms.Control.Click> событием. Можно запрограммировать приложение для выполнения некоторых операций, в зависимости от состояния флажка.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Ответ на щелчок элемента управления CheckBox  
  
1.  В <xref:System.Windows.Forms.Control.Click> обработчик событий, используйте <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство, чтобы определить состояние элемента управления и выполните необходимое действие.  
  
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
    >  Если пользователь пытается дважды щелкните <xref:System.Windows.Forms.CheckBox> управления, каждый щелчок будет обрабатываться отдельно, то есть, <xref:System.Windows.Forms.CheckBox> элемент управления не поддерживает событие двойного щелчка.  
  
    > [!NOTE]
    >  Когда <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> свойство `true` (по умолчанию), <xref:System.Windows.Forms.CheckBox> автоматически установлен или снят, при щелчке. В противном случае необходимо вручную задать <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство при <xref:System.Windows.Forms.Control.Click> событием.  
  
     Можно также использовать <xref:System.Windows.Forms.CheckBox> управления, чтобы определить направление действий.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Чтобы определить порядок действий при установке флажка нажата  
  
1.  Использование инструкции case для запроса значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойства, чтобы определить направление действий. При <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> может возвратить три возможных значения, представляющие флажок, поле снятому или сторонним неопределенное состояние, в котором отображается поле с серым цветом. внешний вид, чтобы указать этот параметр недоступен.  
  
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
    >  Когда <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` для обоих <xref:System.Windows.Forms.CheckState.Checked> и <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.CheckBox>  
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
