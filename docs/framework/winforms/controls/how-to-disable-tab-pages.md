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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="480e0-102">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="480e0-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="480e0-103">В некоторых случаях может потребоваться ограничить доступ к данным, доступным в приложении Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="480e0-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="480e0-104">Примером этого может быть при наличии данных, отображаемых на страницах вкладок элемента управления вкладками; Администраторы могут иметь сведения на странице вкладки, который требуется запретить запись гостя или пользователям более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="480e0-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="480e0-105">Чтобы отключить страницы вкладок программными средствами</span><span class="sxs-lookup"><span data-stu-id="480e0-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="480e0-106">Напишите код для обработки управления "Вкладка" <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="480e0-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="480e0-107">Это событие, которое возникает при переключении с одной вкладки к следующему.</span><span class="sxs-lookup"><span data-stu-id="480e0-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="480e0-108">Проверьте учетные данные.</span><span class="sxs-lookup"><span data-stu-id="480e0-108">Check credentials.</span></span> <span data-ttu-id="480e0-109">В зависимости от данных, выводимых, вы можете проверить имя пользователя, который пользователь вошел в систему или другие формы учетные данные, прежде чем предоставить пользователю получить доступ к вкладке.</span><span class="sxs-lookup"><span data-stu-id="480e0-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="480e0-110">Если у пользователя есть соответствующие учетные данные, отображаться вкладка, которая была нажата.</span><span class="sxs-lookup"><span data-stu-id="480e0-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="480e0-111">Если пользователь не имеет соответствующих учетных данных, окно сообщения, или другой пользовательский интерфейс, указывающий, что они не имеют доступа и вернуться на вкладку начальной.</span><span class="sxs-lookup"><span data-stu-id="480e0-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="480e0-112">При реализации этих возможностей в приложении можно выполнять проверку учетных данных во время формы <xref:System.Windows.Forms.Form.Load> событий.</span><span class="sxs-lookup"><span data-stu-id="480e0-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="480e0-113">Это позволит скрывать вкладку до отображения пользовательского интерфейса, это более предпочтительно в программировании.</span><span class="sxs-lookup"><span data-stu-id="480e0-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="480e0-114">Используемые ниже методы (проверка учетных данных и отключение вкладки в <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> событий) для демонстрационных целей.</span><span class="sxs-lookup"><span data-stu-id="480e0-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="480e0-115">При необходимости при наличии более двух вкладок, можно отобразите вкладку отличается от исходного.</span><span class="sxs-lookup"><span data-stu-id="480e0-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="480e0-116">В следующем примере <xref:System.Windows.Forms.CheckBox> управления используется вместо проверки учетных данных, в качестве критерия для доступа к вкладке зависит от приложения.</span><span class="sxs-lookup"><span data-stu-id="480e0-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="480e0-117">Когда <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> события, если проверка учетных данных имеет значение true (то есть флажок установлен) и выбрана вкладка `TabPage2` (вкладка с конфиденциальными данными, в этом примере), затем `TabPage2` отображается.</span><span class="sxs-lookup"><span data-stu-id="480e0-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="480e0-118">В противном случае `TabPage3` отображается и отображается окно сообщения об отсутствии необходимых прав доступа.</span><span class="sxs-lookup"><span data-stu-id="480e0-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="480e0-119">В следующем примере кода предполагается наличие формы с <xref:System.Windows.Forms.CheckBox> управления (`CredentialCheck`) и <xref:System.Windows.Forms.TabControl> управления с тремя вкладками.</span><span class="sxs-lookup"><span data-stu-id="480e0-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="480e0-120">(Visual C#, Visual C++) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="480e0-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="480e0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="480e0-121">See Also</span></span>  
 [<span data-ttu-id="480e0-122">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="480e0-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="480e0-123">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="480e0-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="480e0-124">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="480e0-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="480e0-125">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="480e0-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
