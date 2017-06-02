---
title: "Практическое руководство. Добавление панелей в элемент управления StatusBar | Microsoft Docs"
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
  - "панели, строки состояния"
  - "строки состояния, добавление панелей"
  - "StatusBar - элемент управления [Windows Forms], добавление панелей"
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Добавление панелей в элемент управления StatusBar
> [!IMPORTANT]
>  Элементы управления <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> заменяют элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> и расширяют их функциональные возможности; однако при необходимости элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> можно сохранить для обратной совместимости и использования в будущем.  
  
 Программируемая область элемента управления [Элемент управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) состоит из экземпляров класса <xref:System.Windows.Forms.StatusBarPanel>.  Они добавляются путем добавления к классу <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
### Добавление панелей в строку состояния  
  
1.  С помощью процедуры создайте панели строки состояния путем добавления их в коллекцию <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  Определите параметры свойств отдельных панелей с помощью индексов, передаваемых через свойство <xref:System.Windows.Forms.StatusBar.Panels%2A>.  
  
     В следующем примере кода в качестве местоположения значка выбрана папка **Мои документы**.  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  Для следующего примера требуется форма с заранее добавленным элементом управления <xref:System.Windows.Forms.StatusBar>.  
  
    > [!NOTE]
    >  Индекс коллекции <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> начинается с нуля, что, соответственно, должно быть учтено в коде.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Collection Editor Dialog Box](http://msdn.microsoft.com/ru-ru/53fb3aad-bffa-4da5-ac89-8438e6fc803c)   
 [Практическое руководство. Определение размера панелей строки состояния](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [Пошаговое руководство. Обновление строки состояния во время выполнения](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Общие сведения об элементе управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)