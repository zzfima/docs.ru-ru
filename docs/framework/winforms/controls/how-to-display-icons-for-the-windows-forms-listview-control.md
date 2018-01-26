---
title: "Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms"
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
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3a19bdd7007a7e47fa1a8ad975112e53c1b6eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms
Windows Forms <xref:System.Windows.Forms.ListView> элемент управления может отображать значки из трех списков изображений. Представления списка, подробности и SmallIcon отображение изображений из списка изображений, указанный в <xref:System.Windows.Forms.ListView.SmallImageList%2A> свойство. В представлении LargeIcon отображается изображений из списка изображений, указанный в <xref:System.Windows.Forms.ListView.LargeImageList%2A> свойство. Представление списка можно также отобразить дополнительный набор значков, заданных <xref:System.Windows.Forms.ListView.StateImageList%2A> свойства рядом с крупных или мелких значков. Дополнительные сведения о списках изображений см. в разделе [компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью компонента ImageList в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Для отображения изображений в представлении списка  
  
1.  Установите соответствующее свойство —<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, или <xref:System.Windows.Forms.ListView.StateImageList%2A>— для существующего <xref:System.Windows.Forms.ImageList> компонентов, которые вы хотите использовать.  
  
     Эти свойства можно задать в конструкторе с помощью окна «Свойства» или в коде.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  Задать <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> или <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> свойство для каждого элемента списка, который содержит значок.  
  
     Эти свойства могут быть заданы в коде или в **редактор коллекции ListViewItem**. Чтобы открыть **редактор коллекции ListViewItem**, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.ListView.Items%2A>свойство **свойства** окна.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
