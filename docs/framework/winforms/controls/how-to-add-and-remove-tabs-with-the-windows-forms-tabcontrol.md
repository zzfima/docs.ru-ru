---
title: "Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7df8b785b2c05acbbec9c17e12e462d755d0cd3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms
По умолчанию <xref:System.Windows.Forms.TabControl> управления содержит два <xref:System.Windows.Forms.TabPage> элементов управления. Получить доступ к этим вкладкам через <xref:System.Windows.Forms.TabControl.TabPages%2A> свойство.  
  
### <a name="to-add-a-tab-programmatically"></a>Чтобы добавить вкладку программными средствами  
  
-   Используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> свойство.  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a>Чтобы удалить вкладку программными средствами  
  
-   Для удаления выбранных вкладок используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> свойство.  
  
     -или-  
  
-   Чтобы удалить все вкладки, используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> свойство.  
  
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
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
