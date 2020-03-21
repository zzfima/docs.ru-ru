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
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182171"
---
# <a name="how-to-disable-tab-pages"></a>Практическое руководство. Блокировка доступа ко вкладкам
В некоторых случаях требуется ограничить доступ к данным, доступным в приложении Windows Forms. Одним из примеров этого может быть, когда данные отображаются на страницах вкладок управления вкладками; администраторы могут иметь информацию на странице вкладок, которую вы хотели бы ограничить от гостевых или пользователей более низкого уровня.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Чтобы программно отключить страницы вкладок  
  
1. Напишите код для обработки <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> события управления вкладками. Это событие, возникает при переходе пользователя с одной вкладки на другую.  
  
2. Проверьте учетные данные. В зависимости от представленной информации, вы можете проверить имя пользователя, с которого пользователь вошел в систему, или какую-либо другую форму учетных данных, прежде чем разрешить пользователю просматривать вкладку.  
  
3. Если пользователь имеет соответствующие учетные данные, отобразите нажатую вкладку. Если пользователь не имеет соответствующих учетных данных, отобразите окно сообщений или другой пользовательский интерфейс, указывающий, что у него нет доступа, и вернитесь к исходной вкладке.  
  
    > [!NOTE]
    > При реализации этой функциональности в производственных приложениях можно выполнить <xref:System.Windows.Forms.Form.Load> эту проверку учетных данных во время события формы. Это позволит вам скрыть вкладку до любого пользовательского интерфейса отображается, что является гораздо более чистым подходом к программированию. Методология, используемая ниже (проверка учетных данных <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> и отключение вкладки во время события) предназначена для иллюстративных целей.  
  
4. Дополнительно, если у вас есть более двух страниц вкладок, отобразите страницу вкладок, отличаемую от оригинала.  
  
     В приведенном ниже <xref:System.Windows.Forms.CheckBox> примере вместо проверки учетных данных используется элементуправления, так как критерии доступа к вкладке будут варьироваться в зависимости от приложения. Когда <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событие поднято, если проверка учетных данных верна (т.е. проверка `TabPage2` флажка проверена) и выбранная `TabPage2` вкладка (вкладка с конфиденциальной информацией, в этом примере), затем отображается. В `TabPage3` противном случае отображается и отображается окно сообщений пользователю, указывая, что у него нет соответствующих привилегий доступа. Приведенный ниже код принимает <xref:System.Windows.Forms.CheckBox> форму`CredentialCheck`с элементом управления () и элементом <xref:System.Windows.Forms.TabControl> управления с тремя страницами вкладок.  
  
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
  
     (Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления TabControl](tabcontrol-control-overview-windows-forms.md)
- [Практическое руководство. Добавление элемента управления на вкладку](how-to-add-a-control-to-a-tab-page.md)
- [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
