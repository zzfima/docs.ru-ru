---
title: "Практическое руководство. Блокировка доступа ко вкладкам | Microsoft Docs"
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
  - "страницы вкладок, скрытие в формах"
  - "TabControl - элемент управления [Windows Forms], отключение страниц"
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Блокировка доступа ко вкладкам
В некоторых ситуациях бывает необходимо ограничить доступ к данным, доступным в приложении Windows Forms.  Например, при отображении данных на вкладках может возникнуть необходимость запретить гостевым пользователям и пользователям нижнего уровня доступ к содержимому одной из вкладок.  
  
### Чтобы отключить страницы вкладок программными средствами  
  
1.  Напишите код для обработки события <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> элемента управления вкладок.  Данное событие происходит при переключении пользователя на очередную вкладку.  
  
2.  Проверьте учетные данные пользователя.  Прежде чем разрешить пользователю просматривать вкладку, можно, в зависимости от предоставленных сведений, проверить имя пользователя, с которым он вошел в систему, или другие учетные данные.  
  
3.  Если учетные данные соответствуют требованиям, отобразите нужную вкладку.  Если у пользователя нет надлежащих учетных данных, выведите диалоговое окно или другой элемент пользовательского интерфейса, указывающий на отсутствие доступа, и вернитесь на исходную вкладку.  
  
    > [!NOTE]
    >  При реализации этой функции в приложении можно выполнять проверку учетных данных в обработчике события <xref:System.Windows.Forms.Form.Load> формы.  Это позволит скрывать вкладку до отображения пользовательского интерфейса, что предпочтительнее с точки зрения стиля программирования.  Используемые ниже методы \(проверка учетных данных и отключение вкладки в обработчике события <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>\) носят чисто иллюстративный характер.  
  
4.  Если страниц вкладок больше двух, можно отобразить вкладку, отличающуюся от первоначальной.  
  
     В приведенном ниже примере вместо проверки учетных данных используется элемент управления <xref:System.Windows.Forms.CheckBox>, поскольку условия доступа к вкладке будут изменяться в зависимости от приложения.  Если при распознавании события <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> проверка учетных данных прошла успешно \(т. е. флажок установлен\) и выбрана вкладка `TabPage2` \(в данном примере — вкладка с конфиденциальными данными\), то вкладка `TabPage2` отображается.  В противном случае отображается вкладка `TabPage3` и открывается окно с сообщением об отсутствии необходимых прав доступа.  Нижеследующий код предполагает наличие формы, в которой имеется элемент управления <xref:System.Windows.Forms.CheckBox> \(`CredentialCheck`\) и элемент управления <xref:System.Windows.Forms.TabControl> с тремя страницами вкладок.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     \(Visual C\#, Visual C\+\+\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## См. также  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)