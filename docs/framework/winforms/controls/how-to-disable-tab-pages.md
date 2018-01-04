---
title: "Практическое руководство. Блокировка доступа ко вкладкам"
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
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2db19d402f32bd43bb7053403428e8055755d017
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-tab-pages"></a>Практическое руководство. Блокировка доступа ко вкладкам
В некоторых случаях может потребоваться ограничить доступ к данным, доступным в приложении Windows Forms. Примером этого может быть при наличии данных, отображаемых на страницах вкладок элемента управления вкладками; Администраторы могут иметь сведения на странице вкладки, который требуется запретить запись гостя или пользователям более низкого уровня.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Чтобы отключить страницы вкладок программными средствами  
  
1.  Напишите код для обработки управления "Вкладка" <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событий. Это событие, которое возникает при переключении с одной вкладки к следующему.  
  
2.  Проверьте учетные данные. В зависимости от данных, выводимых, вы можете проверить имя пользователя, который пользователь вошел в систему или другие формы учетные данные, прежде чем предоставить пользователю получить доступ к вкладке.  
  
3.  Если у пользователя есть соответствующие учетные данные, отображаться вкладка, которая была нажата. Если пользователь не имеет соответствующих учетных данных, окно сообщения, или другой пользовательский интерфейс, указывающий, что они не имеют доступа и вернуться на вкладку начальной.  
  
    > [!NOTE]
    >  При реализации этих возможностей в приложении можно выполнять проверку учетных данных во время формы <xref:System.Windows.Forms.Form.Load> событий. Это позволит скрывать вкладку до отображения пользовательского интерфейса, это более предпочтительно в программировании. Используемые ниже методы (проверка учетных данных и отключение вкладки в <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событий) для демонстрационных целей.  
  
4.  При необходимости при наличии более двух вкладок, можно отобразите вкладку отличается от исходного.  
  
     В следующем примере <xref:System.Windows.Forms.CheckBox> управления используется вместо проверки учетных данных, в качестве критерия для доступа к вкладке зависит от приложения. Когда <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> события, если проверка учетных данных имеет значение true (то есть флажок установлен) и выбрана вкладка `TabPage2` (вкладка с конфиденциальными данными, в этом примере), затем `TabPage2` отображается. В противном случае `TabPage3` отображается и отображается окно сообщения об отсутствии необходимых прав доступа. В следующем примере кода предполагается наличие формы с <xref:System.Windows.Forms.CheckBox> управления (`CredentialCheck`) и <xref:System.Windows.Forms.TabControl> управления с тремя вкладками.  
  
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
  
     (Visual C#, Visual C++) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
