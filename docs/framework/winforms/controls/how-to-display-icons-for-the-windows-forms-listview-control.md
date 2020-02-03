---
title: Отображение значков для элемента управления ListView
ms.date: 03/30/2017
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
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744503"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.ListView> может отображать значки из трех списков изображений. В представлениях List, Details и маленькие значки отображаются изображения из списка изображений, указанного в свойстве <xref:System.Windows.Forms.ListView.SmallImageList%2A>. В представлении LargeIcon отображаются изображения из списка изображений, указанного в свойстве <xref:System.Windows.Forms.ListView.LargeImageList%2A>. В представлении списка также может отображаться дополнительный набор значков, установленный в свойстве <xref:System.Windows.Forms.ListView.StateImageList%2A> рядом с большим или мелким значками. Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции по добавлению или удалению изображений с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Отображение изображений в представлении списка  
  
1. Задайте соответствующее свойство (<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>или <xref:System.Windows.Forms.ListView.StateImageList%2A>) для существующего компонента <xref:System.Windows.Forms.ImageList>, который вы хотите использовать.  
  
     Эти свойства можно задать в конструкторе с помощью окно свойств или в коде.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Задайте свойство <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> или <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> для каждого элемента списка со связанным значком.  
  
     Эти свойства можно задать в коде или в **редакторе коллекции ListViewItem**. Чтобы открыть **Редактор коллекции ListViewItem**, нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A> в окне **свойства** .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Компонент ImageList](imagelist-component-windows-forms.md)
