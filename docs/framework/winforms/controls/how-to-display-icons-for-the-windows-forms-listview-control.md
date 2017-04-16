---
title: "Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms | Microsoft Docs"
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
  - "значки, отображение для элементов управления ListView"
  - "ImageList - компонент [Windows Forms], с элементом управления ListView"
  - "представления списков, отображение значков"
  - "списки, отображение значков"
  - "ListView - элемент управления [Windows Forms], отображение значков"
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms
В элементе управления Windows Forms <xref:System.Windows.Forms.ListView> могут отображаться значки из трех списков рисунков.  Представления List, Details и SmallIcon отображают рисунки из списка рисунков, указанного в свойстве <xref:System.Windows.Forms.ListView.SmallImageList%2A>.  Представление LargeIcon отображает рисунки из списка рисунков, указанного в свойстве <xref:System.Windows.Forms.ListView.LargeImageList%2A>.  В представлении в виде списка также имеется возможность отобразить дополнительный набор значков, заданных в свойстве <xref:System.Windows.Forms.ListView.StateImageList%2A>, рядом с крупными или мелкими значками.  Дополнительные сведения о списках рисунков см. в разделах [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### Чтобы отобразить рисунки в представлении в виде списка  
  
1.  Задайте соответствующее свойство: <xref:System.Windows.Forms.ListView.LargeImageList%2A>, <xref:System.Windows.Forms.ListView.StateImageList%2A> или <xref:System.Windows.Forms.ImageList> для существующего компонента <xref:System.Windows.Forms.ListView.SmallImageList%2A>, который необходимо использовать.  
  
     Эти свойства можно задать в окне "Свойства" конструктора или в коде.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  Задайте свойство <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> или <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> для каждого элемента списка, имеющего связанный значок.  
  
     Эти свойства можно задать в коде или в **Редакторе коллекций ListViewItem**.  Чтобы открыть **Редактор коллекций ListViewItem**, нажмите кнопку с троеточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A> в окне **Свойства**.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## См. также  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)