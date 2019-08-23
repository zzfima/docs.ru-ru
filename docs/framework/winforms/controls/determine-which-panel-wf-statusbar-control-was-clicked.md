---
title: Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms
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
ms.openlocfilehash: 6229d8965949641105cd0e9708474c3249d52d1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965724"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> Элементы управления <xref:System.Windows.Forms.ToolStripStatusLabel> и заменяют и добавляют функциональные возможности в элементы управления и, однако, элементы управления и сохраняются для обратной совместимости и использования в будущем, если <xref:System.Windows.Forms.StatusStrip> выбрали.  
  
 Чтобы программировать элемент управления [StatusBar](statusbar-control-windows-forms.md) для реагирования на нажатия пользователем, используйте оператор case в <xref:System.Windows.Forms.StatusBar.PanelClick> событии. Событие содержит аргумент (аргумент Panel), который содержит ссылку на щелчок <xref:System.Windows.Forms.StatusBarPanel>. Используя эту ссылку, можно определить индекс для нажатой панели и соответствующим образом программировать.  
  
> [!NOTE]
> Убедитесь, что <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойство элемента управления имеет значение `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Определение того, какая панель была нажата  
  
1. `switch case` `Select Case` В обработчике C# событий используйте оператор (в Visual Basic) или (визуальный или визуальный C++), чтобы определить, какая панель была нажата, проверив индекс нажатой панели в аргументах события. <xref:System.Windows.Forms.StatusBar.PanelClick>  
  
     В следующем примере кода требуется присутствие, в <xref:System.Windows.Forms.StatusBar> форме, элемента управления, `StatusBar1`и двух <xref:System.Windows.Forms.StatusBarPanel> объектов, `StatusBarPanel1` и `StatusBarPanel2`.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Практическое руководство. Установка размера панелей строки состояния](how-to-set-the-size-of-status-bar-panels.md)
- [Пошаговое руководство: Обновление сведений в строке состояния во время выполнения](walkthrough-updating-status-bar-information-at-run-time.md)
- [Общие сведения об элементе управления StatusBar](statusbar-control-overview-windows-forms.md)
