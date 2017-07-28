---
title: "Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms | Microsoft Docs"
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
  - "Panel - элемент управления [Windows Forms], определение щелчка"
  - "PanelClick - событие, определение выбранной панели"
  - "панели, определение выбранной"
  - "строки состояния, определение выбранной панели"
  - "StatusBar - элемент управления [Windows Forms], кодирование событий выбора панели"
  - "StatusBar - элемент управления [Windows Forms], определение выбранной панели"
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms
> [!IMPORTANT]
>  Элементы управления <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> заменяют элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> и расширяют их функциональные возможности; однако при необходимости элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> можно сохранить для обратной совместимости и использования в будущем.  
  
 Для программирования элемента управления [Элемент управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) на реагирование на щелчок мышью пользователя используется оператор условия в событии <xref:System.Windows.Forms.StatusBar.PanelClick>.  Событие содержит аргумент \(аргумент области\), содержащий ссылку на нажатый элемент управления <xref:System.Windows.Forms.StatusBarPanel>.  Используя эту ссылку, можно определить индекс выбранной панели и соответствующим образом запрограммировать ее.  
  
> [!NOTE]
>  Убедитесь, что свойство <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> элемента управления <xref:System.Windows.Forms.StatusBar> имеет значение `true`.  
  
### Чтобы определить, в какой области был щелчок  
  
1.  В обработчике событий <xref:System.Windows.Forms.StatusBar.PanelClick> используйте оператор `Select Case` \(в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) или `switch case` \(в [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] или [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\), чтобы определить, какая панель была выбрана, посредством проверки индекса выбранной панели в аргументах события.  
  
     В следующем примере кода требуется наличие в форме элемента управления <xref:System.Windows.Forms.StatusBar>, `StatusBar1` и двух объектов <xref:System.Windows.Forms.StatusBarPanel>,`StatusBarPanel1` и`StatusBarPanel2`.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Практическое руководство. Определение размера панелей строки состояния](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [Пошаговое руководство. Обновление строки состояния во время выполнения](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Общие сведения об элементе управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)