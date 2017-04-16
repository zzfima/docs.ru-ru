---
title: "Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms | Microsoft Docs"
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
  - "страницы вкладок"
  - "TabControl - элемент управления [Windows Forms], добавление и удаление вкладок"
  - "TabPage - элемент управления"
  - "вкладки, добавление на страницу"
  - "вкладки, удаления из страниц"
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms
По умолчанию элемент управления <xref:System.Windows.Forms.TabControl> содержит два элемента управления <xref:System.Windows.Forms.TabPage>.  Доступ к этим вкладкам возможен посредством свойства <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
### Добавление вкладки программными средствами  
  
-   Используйте метод <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> свойства <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### Удаление вкладки программными средствами  
  
-   Для удаления выбранных вкладок используйте метод <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> свойства <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
     \-или\-  
  
-   Для удаления всех вкладок используйте метод <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> свойства <xref:System.Windows.Forms.TabControl.TabPages%2A>.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## См. также  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)