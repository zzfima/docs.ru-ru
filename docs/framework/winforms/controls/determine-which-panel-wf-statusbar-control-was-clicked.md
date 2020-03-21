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
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> Элементы <xref:System.Windows.Forms.ToolStripStatusLabel> управления заменяют и <xref:System.Windows.Forms.StatusBar> добавляют <xref:System.Windows.Forms.StatusBarPanel> функциональность и элементы управления; однако, <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> и элементы управления сохраняются как для обратной совместимости, так и для будущего использования, если вы выберете.  
  
 Чтобы запрограммировать элемент [управления StatusBar](statusbar-control-windows-forms.md) для ответа на клики пользователей, используйте выписку по случаю в событии. <xref:System.Windows.Forms.StatusBar.PanelClick> Событие содержит аргумент (аргумент панели), который содержит ссылку <xref:System.Windows.Forms.StatusBarPanel>на нажмите . Используя эту ссылку, вы можете определить индекс нажатой панели, и программы соответственно.  
  
> [!NOTE]
> Убедитесь, <xref:System.Windows.Forms.StatusBar> что <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойство элемента управления настроено на. `true`  
  
### <a name="to-determine-which-panel-was-clicked"></a>Определить, какая панель была нажат  
  
1. В <xref:System.Windows.Forms.StatusBar.PanelClick> обработчике `Select Case` событий используйте (в Visual Basic) или `switch case` (Visual C или Visual C) выписку, чтобы определить, какая панель была нажата, изучая индекс нажатой панели в аргументах события.  
  
     Следующий пример кода требует присутствия, на <xref:System.Windows.Forms.StatusBar> форме, `StatusBar1`элемента <xref:System.Windows.Forms.StatusBarPanel> управления, и двух объектов, `StatusBarPanel1` и `StatusBarPanel2`.  
  
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
  
     (Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Определение размера панелей строки состояния](how-to-set-the-size-of-status-bar-panels.md)
- [Пошаговое руководство. Обновление строки состояния во время выполнения](walkthrough-updating-status-bar-information-at-run-time.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
