---
title: Практическое руководство. Блокировка доступа ко вкладкам
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967141"
---
# <a name="how-to-disable-tab-pages"></a>Практическое руководство. Блокировка доступа ко вкладкам
В некоторых случаях потребуется ограничить доступ к данным, доступным в приложении Windows Forms. Одним из примеров этого может быть то, что данные отображаются на вкладках вкладки элемента управления «вкладка». Администраторы могут получить сведения на странице вкладки, которую вы бы хотели бы ограничить от гостей или пользователей низкого уровня.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Отключение страниц вкладок программными средствами  
  
1. Напишите код, обрабатывающий <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событие элемента управления Tab. Это событие возникает, когда пользователь переключается с одной вкладки на следующую.  
  
2. Проверьте учетные данные. В зависимости от представленных сведений может потребоваться проверить имя пользователя, выполнившего вход, или другую форму учетных данных, прежде чем разрешить пользователю просматривать вкладку.  
  
3. Если у пользователя есть соответствующие учетные данные, отобразите вкладку, которая была нажата. Если у пользователя нет соответствующих учетных данных, отобразите окно сообщения или другой пользовательский интерфейс, указывающий на то, что у него нет доступа, и вернитесь на начальную вкладку.  
  
    > [!NOTE]
    > При реализации этой функции в рабочих приложениях эту проверку учетных данных можно выполнить во время <xref:System.Windows.Forms.Form.Load> события формы. Это позволит скрыть вкладку перед отображением пользовательского интерфейса, что является намного более гибким подходом к программированию. Методология, использованная ниже (проверка учетных данных и отключение вкладки <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> во время события), относится к наглядным целям.  
  
4. При необходимости, если имеется более двух страниц вкладок, отобразите страницу вкладок, отличную от исходной.  
  
     В приведенном ниже <xref:System.Windows.Forms.CheckBox> примере элемент управления используется вместо проверки учетных данных, так как критерии доступа к вкладке будут зависеть от приложения. При возникновении `TabPage2`события, если проверка учетных данных имеет значение true (то есть флажок установлен), а выбранная вкладка — (вкладка с конфиденциальной информацией в этом примере), то `TabPage2` отображается. <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> В противном случае отображается, `TabPage3` и пользователю отображается окно сообщения, указывающее, что у них нет соответствующих прав доступа. В приведенном ниже коде предполагается форма <xref:System.Windows.Forms.CheckBox> с элементом`CredentialCheck`управления () <xref:System.Windows.Forms.TabControl> и элементом управления с тремя страницами вкладок.  
  
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
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления TabControl](tabcontrol-control-overview-windows-forms.md)
- [Практическое руководство. Добавление элемента управления на страницу вкладки](how-to-add-a-control-to-a-tab-page.md)
- [Практическое руководство. Добавление и удаление вкладок с помощью элемента Windows Forms TabControl](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Практическое руководство. Изменение внешнего вида Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
