---
title: "Практическое руководство. Определение размера панелей строки состояния | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "панели, установка размера в строке состояния"
  - "строки состояния, установка размера панели"
  - "StatusBar - элемент управления [Windows Forms], размер панели"
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Определение размера панелей строки состояния
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.ToolStripStatusLabel> заменяет элемент управления <xref:System.Windows.Forms.StatusBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.StatusBar> можно сохранить для обратной совместимости и использования в будущем.  
  
 Каждый экземпляр класса <xref:System.Windows.Forms.StatusBarPanel> в элементе управления [Элемент управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) имеет ряд динамических свойств, определяющих его ширину и изменение размеров во время выполнения.  
  
### Настройка размера панели  
  
1.  В процедуре установите свойства <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A> и <xref:System.Windows.Forms.StatusBarPanel.Width%2A> \(или любые их подмножества\) для панелей строк состояния , используя коэффициент, подставляемый через свойство <xref:System.Windows.Forms.StatusBar.Panels%2A> коллекции <xref:System.Windows.Forms.StatusBarPanel>.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Пошаговое руководство. Обновление строки состояния во время выполнения](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Общие сведения об элементе управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)