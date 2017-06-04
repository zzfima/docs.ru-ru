---
title: "Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "checked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "флажки, использование для установки параметров"
  - "CheckBox - элемент управления [Windows Forms], установленное состояние"
  - "CheckBox - элемент управления [Windows Forms], использование для установки параметров"
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox> используется для предоставления пользователями параметров типа "Истина\/ложь" или "Да\/нет".  Когда флажок установлен, он отображается в элементе управления.  
  
### Настройка параметров с помощью элементов управления CheckBox  
  
1.  Определите значение свойства <xref:System.Windows.Forms.CheckBox.Checked%2A>, чтобы определить его состояние, и задайте параметр с помощью этого значения.  
  
     В приведенном ниже примере кода при вызове события <xref:System.Windows.Forms.CheckBox.CheckedChanged> элемента управления <xref:System.Windows.Forms.CheckBox> для свойства формы <xref:System.Windows.Forms.Control.AllowDrop%2A> задается значение `false`, если флажок установлен.  Это используется в случаях, когда требуется ограничить действия пользователя.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.CheckBox>   
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)