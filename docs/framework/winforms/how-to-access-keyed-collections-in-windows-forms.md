---
title: "Практическое руководство. Доступ к коллекциям с ключом в Windows Forms"
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
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 852e82aff12dc39adeba6ea2dada5934ae55f951
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Практическое руководство. Доступ к коллекциям с ключом в Windows Forms
-   Отдельные элементы коллекции доступны по ключу. Эта функция будет добавлен во многих классах коллекций, которые обычно используются приложениями Windows Forms. Ниже перечислены некоторые из классов коллекций, которые имеют доступ коллекции с ключом.  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Ключ, связанный с элементом в коллекции, обычно является имя элемента. Следующие процедуры показывают, как использовать классы коллекций для выполнения стандартных задач.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Чтобы найти и передать фокус вложенному элементу управления в коллекции элементов управления  
  
-   Используйте <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> и <xref:System.Windows.Forms.Control.Focus%2A> методов, чтобы указать имя элемента управления, чтобы найти и передать фокус.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Для доступа к изображению в коллекции изображений  
  
-   Используйте <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> свойство, чтобы указать имя образа, которым требуется доступ.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Чтобы задать страницу вкладки в качестве выбранной вкладки  
  
-   Используйте <xref:System.Windows.Forms.TabControl.SelectedTab%2A> свойство вместе с <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> свойство, чтобы указать имя вкладки, которую следует задать в качестве выбранной вкладки.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
