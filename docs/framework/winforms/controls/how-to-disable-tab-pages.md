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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="7cb8e-102">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="7cb8e-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="7cb8e-103">В некоторых случаях требуется ограничить доступ к данным, доступным в приложении Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="7cb8e-104">Одним из примеров этого может быть, когда данные отображаются на страницах вкладок управления вкладками; администраторы могут иметь информацию на странице вкладок, которую вы хотели бы ограничить от гостевых или пользователей более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="7cb8e-105">Чтобы программно отключить страницы вкладок</span><span class="sxs-lookup"><span data-stu-id="7cb8e-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="7cb8e-106">Напишите код для обработки <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> события управления вкладками.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="7cb8e-107">Это событие, возникает при переходе пользователя с одной вкладки на другую.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="7cb8e-108">Проверьте учетные данные.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-108">Check credentials.</span></span> <span data-ttu-id="7cb8e-109">В зависимости от представленной информации, вы можете проверить имя пользователя, с которого пользователь вошел в систему, или какую-либо другую форму учетных данных, прежде чем разрешить пользователю просматривать вкладку.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="7cb8e-110">Если пользователь имеет соответствующие учетные данные, отобразите нажатую вкладку.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="7cb8e-111">Если пользователь не имеет соответствующих учетных данных, отобразите окно сообщений или другой пользовательский интерфейс, указывающий, что у него нет доступа, и вернитесь к исходной вкладке.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7cb8e-112">При реализации этой функциональности в производственных приложениях можно выполнить <xref:System.Windows.Forms.Form.Load> эту проверку учетных данных во время события формы.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="7cb8e-113">Это позволит вам скрыть вкладку до любого пользовательского интерфейса отображается, что является гораздо более чистым подходом к программированию.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="7cb8e-114">Методология, используемая ниже (проверка учетных данных <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> и отключение вкладки во время события) предназначена для иллюстративных целей.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="7cb8e-115">Дополнительно, если у вас есть более двух страниц вкладок, отобразите страницу вкладок, отличаемую от оригинала.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="7cb8e-116">В приведенном ниже <xref:System.Windows.Forms.CheckBox> примере вместо проверки учетных данных используется элементуправления, так как критерии доступа к вкладке будут варьироваться в зависимости от приложения.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="7cb8e-117">Когда <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событие поднято, если проверка учетных данных верна (т.е. проверка `TabPage2` флажка проверена) и выбранная `TabPage2` вкладка (вкладка с конфиденциальной информацией, в этом примере), затем отображается.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="7cb8e-118">В `TabPage3` противном случае отображается и отображается окно сообщений пользователю, указывая, что у него нет соответствующих привилегий доступа.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="7cb8e-119">Приведенный ниже код принимает <xref:System.Windows.Forms.CheckBox> форму`CredentialCheck`с элементом управления () и элементом <xref:System.Windows.Forms.TabControl> управления с тремя страницами вкладок.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="7cb8e-120">(Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="7cb8e-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7cb8e-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7cb8e-121">See also</span></span>

- [<span data-ttu-id="7cb8e-122">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="7cb8e-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="7cb8e-123">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="7cb8e-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="7cb8e-124">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cb8e-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="7cb8e-125">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cb8e-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
