---
title: "How to: Access Keyed Collections in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "keyed collections [Windows Forms]"
  - "collections, accessing with keys"
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Access Keyed Collections in Windows Forms
-   Доступ к отдельным элементам коллекции можно получить с помощью ключа.  Эта функция добавлена для многих классов коллекций, которые обычно используются приложениями Windows Forms.  Ниже перечислены некоторые из классов коллекций, имеющих доступные с помощью ключа коллекции.  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Ключ, связанный с элементом коллекции, обычно является именем элемента.  В следующих процедурах показано, как использовать классы коллекций для выполнения общих задач.  
  
### Чтобы найти и передать фокус вложенному элементу управления в коллекции элементов управления, выполните следующие действия.  
  
-   Используйте методы <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> и <xref:System.Windows.Forms.Control.Focus%2A>, чтобы указать имя элемента управления для поиска и передачи фокуса.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### Для доступа к изображению в коллекции изображений, выполните следующие действия.  
  
-   Используйте свойство <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> для указания имени изображения, к которому требуется получить доступ.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### Чтобы установить вкладку в качестве выбранной вкладки, выполните следующие действия.  
  
-   Используйте свойство <xref:System.Windows.Forms.TabControl.SelectedTab%2A> вместе со свойством <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> для указания имени вкладки, которую следует установить в качестве выбранной.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## См. также  
 [Getting Started with Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)   
 [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)