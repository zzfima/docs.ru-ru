---
title: Определение того, какая панель в элементе управления StatusBar была нажата
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746008"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и добавляют функции в элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel>. Однако элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> сохраняются как для обратной совместимости, так и для будущего использования, если вы решили.  
  
 Чтобы программировать элемент управления [StatusBar](statusbar-control-windows-forms.md) для реагирования на нажатия пользователем, используйте инструкцию CASE в событии <xref:System.Windows.Forms.StatusBar.PanelClick>. Событие содержит аргумент (аргумент Panel), который содержит ссылку на <xref:System.Windows.Forms.StatusBarPanel>. Используя эту ссылку, можно определить индекс для нажатой панели и соответствующим образом программировать.  
  
> [!NOTE]
> Убедитесь, что для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> элемента управления <xref:System.Windows.Forms.StatusBar> задано значение `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Определение того, какая панель была нажата  
  
1. В обработчике событий <xref:System.Windows.Forms.StatusBar.PanelClick> используйте инструкцию `Select Case` (в Visual Basic) или `switch case` (визуальный C# или C++визуальный элемент), чтобы определить, какая панель была нажата, проверив индекс нажатой панели в аргументах события.  
  
     В следующем примере кода требуется присутствие, в форме, элемента управления <xref:System.Windows.Forms.StatusBar>, `StatusBar1`и двух <xref:System.Windows.Forms.StatusBarPanel> объектов, `StatusBarPanel1` и `StatusBarPanel2`.  
  
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
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Определение размера панелей строки состояния](how-to-set-the-size-of-status-bar-panels.md)
- [Пошаговое руководство. Обновление строки состояния во время выполнения](walkthrough-updating-status-bar-information-at-run-time.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
