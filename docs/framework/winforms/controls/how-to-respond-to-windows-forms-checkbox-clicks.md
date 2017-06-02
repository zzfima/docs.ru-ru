---
title: "Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "флажки, отклик на события"
  - "CheckBox - элемент управления [Windows Forms], события Click"
  - "Click - событие, CheckBox - элемент управления"
  - "двойной щелчок"
  - "события [Windows Forms], события Click"
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Если щелкнуть элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox>, происходит событие <xref:System.Windows.Forms.Control.Click>.  В приложении можно задать выполнение определенного действия в зависимости от состояния флажка.  
  
### Чтобы ответить на щелчок элемента управления CheckBox  
  
1.  В обработчике события <xref:System.Windows.Forms.Control.Click> с помощью свойства <xref:System.Windows.Forms.CheckBox.Checked%2A> определите состояние элемента управления и выполните необходимое действие.  
  
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
    >  Если дважды щелкнуть элемент управления <xref:System.Windows.Forms.CheckBox>, каждый щелчок будет обрабатываться отдельно; другими словами, элемент управления <xref:System.Windows.Forms.CheckBox> не поддерживает событие двойного щелчка.  
  
    > [!NOTE]
    >  Если для свойства <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> задано значение `true` \(значение по умолчанию\), элемент управления <xref:System.Windows.Forms.CheckBox> автоматически меняет состояние при щелчке.  В противном случае необходимо вручную задать свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> при возникновении события <xref:System.Windows.Forms.Control.Click>.  
  
     Элемент управления <xref:System.Windows.Forms.CheckBox> используется также для определения образа действия.  
  
### Чтобы определить образ действия при щелчке флажка  
  
1.  Используйте оператор case для запроса значения свойства <xref:System.Windows.Forms.CheckBox.CheckState%2A>, чтобы определить образ действия.  Если для свойства <xref:System.Windows.Forms.CheckBox.ThreeState%2A> задано значение `true`, свойство <xref:System.Windows.Forms.CheckBox.CheckState%2A> возвращает одно из трех возможных значений, соответствующих установленному флажку, снятому флажку или неопределенному состоянию флажка, при котором поле флажка отображается затененным, что означает недоступность параметра.  
  
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
    >  Если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` как для <xref:System.Windows.Forms.CheckState>, так и для <xref:System.Windows.Forms.CheckState>.  
  
## См. также  
 <xref:System.Windows.Forms.CheckBox>   
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)