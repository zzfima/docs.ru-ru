---
title: Практическое руководство. Определение размера панелей строки состояния
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
ms.openlocfilehash: 4ba0f7f02b548a5d9ea1a99605a668f449b3e4a9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923629"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Практическое руководство. Определение размера панелей строки состояния
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> заменяет элемент управления <xref:System.Windows.Forms.StatusBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.StatusBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Каждый экземпляр <xref:System.Windows.Forms.StatusBarPanel> класса в элементе управления [StatusBar](statusbar-control-windows-forms.md) имеет ряд динамических свойств, определяющих его ширину и поведение при изменении размера во время выполнения.  
  
### <a name="to-set-the-size-of-a-panel"></a>Задание размера панели  
  
1. В процедуре <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>задайте свойства, <xref:System.Windows.Forms.StatusBarPanel.Width%2A> <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>и (или любое подмножество) для панелей <xref:System.Windows.Forms.StatusBar.Panels%2A> строки состояния, используя индекс, передаваемый через свойство <xref:System.Windows.Forms.StatusBarPanel> коллекции.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Пошаговое руководство: Обновление сведений в строке состояния во время выполнения](walkthrough-updating-status-bar-information-at-run-time.md)
- [Практическое руководство. Определите, какая панель элемента управления Windows Forms StatusBar была нажата](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
