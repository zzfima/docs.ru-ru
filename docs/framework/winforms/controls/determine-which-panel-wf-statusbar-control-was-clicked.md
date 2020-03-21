---
title: Определить, какая панель в statusBar управления нажал
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182363"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="3ad10-102">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ad10-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3ad10-103"><xref:System.Windows.Forms.StatusStrip> Элементы <xref:System.Windows.Forms.ToolStripStatusLabel> управления заменяют и <xref:System.Windows.Forms.StatusBar> добавляют <xref:System.Windows.Forms.StatusBarPanel> функциональность и элементы управления; однако, <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> и элементы управления сохраняются как для обратной совместимости, так и для будущего использования, если вы выберете.</span><span class="sxs-lookup"><span data-stu-id="3ad10-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="3ad10-104">Чтобы запрограммировать элемент [управления StatusBar](statusbar-control-windows-forms.md) для ответа на клики пользователей, используйте выписку по случаю в событии. <xref:System.Windows.Forms.StatusBar.PanelClick></span><span class="sxs-lookup"><span data-stu-id="3ad10-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="3ad10-105">Событие содержит аргумент (аргумент панели), который содержит ссылку <xref:System.Windows.Forms.StatusBarPanel>на нажмите .</span><span class="sxs-lookup"><span data-stu-id="3ad10-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="3ad10-106">Используя эту ссылку, вы можете определить индекс нажатой панели, и программы соответственно.</span><span class="sxs-lookup"><span data-stu-id="3ad10-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ad10-107">Убедитесь, <xref:System.Windows.Forms.StatusBar> что <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойство элемента управления настроено на. `true`</span><span class="sxs-lookup"><span data-stu-id="3ad10-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="3ad10-108">Определить, какая панель была нажат</span><span class="sxs-lookup"><span data-stu-id="3ad10-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="3ad10-109">В <xref:System.Windows.Forms.StatusBar.PanelClick> обработчике `Select Case` событий используйте (в Visual Basic) или `switch case` (Visual C или Visual C) выписку, чтобы определить, какая панель была нажата, изучая индекс нажатой панели в аргументах события.</span><span class="sxs-lookup"><span data-stu-id="3ad10-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="3ad10-110">Следующий пример кода требует присутствия, на <xref:System.Windows.Forms.StatusBar> форме, `StatusBar1`элемента <xref:System.Windows.Forms.StatusBarPanel> управления, и двух объектов, `StatusBarPanel1` и `StatusBarPanel2`.</span><span class="sxs-lookup"><span data-stu-id="3ad10-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="3ad10-111">(Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="3ad10-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ad10-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3ad10-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="3ad10-113">Практическое руководство. Определение размера панелей строки состояния</span><span class="sxs-lookup"><span data-stu-id="3ad10-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="3ad10-114">Пошаговое руководство. Обновление строки состояния во время выполнения</span><span class="sxs-lookup"><span data-stu-id="3ad10-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="3ad10-115">Общие сведения об элементе управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="3ad10-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
