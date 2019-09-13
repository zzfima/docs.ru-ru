---
title: Практическое руководство. Доступ к коллекциям с ключом в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928525"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>Практическое руководство. Доступ к коллекциям с ключом в Windows Forms

- К отдельным элементам коллекции можно обращаться по ключу. Эта функция добавлена во многие классы коллекций, которые обычно используются приложениями Windows Forms. В следующем списке показаны некоторые классы коллекций, имеющие доступные коллекции с ключом:  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 Ключом, связанным с элементом в коллекции, обычно является имя элемента. В следующих процедурах показано, как использовать классы коллекций для выполнения стандартных задач.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>Поиск и передача фокуса вложенному элементу управления в коллекции элементов управления  
  
- Используйте методы <xref:System.Windows.Forms.Control.Focus%2A> и, чтобы указать имя элемента управления, который нужно найти, и присвоить ему фокус. <xref:System.Windows.Forms.Control.ControlCollection.Find%2A>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>Получение доступа к изображению в коллекции изображений  
  
- <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> Используйте свойство, чтобы указать имя изображения, к которому требуется получить доступ.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>Задание страницы вкладки в качестве выбранной вкладки  
  
- Используйте свойство вместе <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> со свойством, чтобы указать имя страницы вкладки, которая будет задана в качестве выбранной вкладки. <xref:System.Windows.Forms.TabControl.SelectedTab%2A>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Приступая к работе с Windows Forms](getting-started-with-windows-forms.md)
- [Практическое руководство. Добавление или удаление образов с помощью компонента Windows Forms ImageList](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
