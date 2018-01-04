---
title: "Практическое руководство. Добавление панелей в элемент управления StatusBar"
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
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96fbfc86183afef047d210fbc13a0944f2b209b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="de966-102">Практическое руководство. Добавление панелей в элемент управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="de966-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="de966-103"><xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> заменить элементы управления и добавить функциональные возможности в <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления можно сохранить для обратной совместимости и использования в будущем, если вы Выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="de966-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="de966-104">Программируемая область [управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) управления состоит из экземпляров <xref:System.Windows.Forms.StatusBarPanel> класса.</span><span class="sxs-lookup"><span data-stu-id="de966-104">The programmable area within a [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="de966-105">Они добавляются путем добавления к <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="de966-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="de966-106">Чтобы добавить панели в строке состояния</span><span class="sxs-lookup"><span data-stu-id="de966-106">To add panels to a status bar</span></span>  
  
1.  <span data-ttu-id="de966-107">С помощью процедуры создания панели строки состояния, добавив их в <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="de966-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="de966-108">Задайте значения свойств для отдельных панелей с помощью индексов, передаваемых через <xref:System.Windows.Forms.StatusBar.Panels%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="de966-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="de966-109">В следующем примере кода путь задан для находится значок **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="de966-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="de966-110">Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows будет содержать эта папка.</span><span class="sxs-lookup"><span data-stu-id="de966-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="de966-111">Эта папка также позволяет уровень доступа к системе минимальной безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="de966-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="de966-112">В следующем примере требуется форма с <xref:System.Windows.Forms.StatusBar> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="de966-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de966-113"><xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> Является коллекция отсчитываемый от нуля, поэтому код должен продолжаться соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="de966-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="de966-114">См. также</span><span class="sxs-lookup"><span data-stu-id="de966-114">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="de966-115">Диалоговое окно редактора коллекции</span><span class="sxs-lookup"><span data-stu-id="de966-115">Collection Editor Dialog Box</span></span>](http://msdn.microsoft.com/en-us/53fb3aad-bffa-4da5-ac89-8438e6fc803c)  
 [<span data-ttu-id="de966-116">Практическое руководство. Определение размера панелей строки состояния</span><span class="sxs-lookup"><span data-stu-id="de966-116">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [<span data-ttu-id="de966-117">Пошаговое руководство. Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="de966-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [<span data-ttu-id="de966-118">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de966-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="de966-119">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="de966-119">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
