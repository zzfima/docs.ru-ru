---
title: Практическое руководство. Задать размер панели строки состояния
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: 5b78463ca273f089f036166f5339977be435ccc9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711945"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a><span data-ttu-id="560a6-102">Практическое руководство. Задать размер панели строки состояния</span><span class="sxs-lookup"><span data-stu-id="560a6-102">How to: Set the Size of Status-Bar Panels</span></span>
> [!NOTE]
>  <span data-ttu-id="560a6-103">Элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> заменяет элемент управления <xref:System.Windows.Forms.StatusBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.StatusBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="560a6-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="560a6-104">Каждый экземпляр <xref:System.Windows.Forms.StatusBarPanel> класса в [элемента управления StatusBar](statusbar-control-windows-forms.md) элемент управления имеет ряд динамических свойств, определяющих его ширину и изменение размеров во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="560a6-104">Each instance of the <xref:System.Windows.Forms.StatusBarPanel> class within a [StatusBar Control](statusbar-control-windows-forms.md) control has a number of dynamic properties that determine its width and resize behavior at run time.</span></span>  
  
### <a name="to-set-the-size-of-a-panel"></a><span data-ttu-id="560a6-105">Чтобы задать размер панели</span><span class="sxs-lookup"><span data-stu-id="560a6-105">To set the size of a panel</span></span>  
  
1.  <span data-ttu-id="560a6-106">В процедуре, задайте <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, и <xref:System.Windows.Forms.StatusBarPanel.Width%2A> свойства (или любое подмножество этой последовательности) для строки состояния панели, с помощью индекса передать <xref:System.Windows.Forms.StatusBar.Panels%2A> свойство <xref:System.Windows.Forms.StatusBarPanel> коллекции.</span><span class="sxs-lookup"><span data-stu-id="560a6-106">In a procedure, set the <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, and <xref:System.Windows.Forms.StatusBarPanel.Width%2A> properties (or any subset therein) for the status-bar panels using their index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property of the <xref:System.Windows.Forms.StatusBarPanel> collection.</span></span>  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="560a6-107">См. также</span><span class="sxs-lookup"><span data-stu-id="560a6-107">See also</span></span>
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="560a6-108">Пошаговое руководство: Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="560a6-108">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="560a6-109">Практическое руководство. Определить, какая из панелей в элемент управления Windows Forms StatusBar была нажата</span><span class="sxs-lookup"><span data-stu-id="560a6-109">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="560a6-110">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="560a6-110">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
