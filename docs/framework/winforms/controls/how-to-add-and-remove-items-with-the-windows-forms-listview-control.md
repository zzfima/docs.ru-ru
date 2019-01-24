---
title: Как выполнить Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 7a4083d54ea85ff7a2e18f7e448f2b967317ac25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544527"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Как выполнить Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
Процесс добавления элемента в формы Windows <xref:System.Windows.Forms.ListView> элемент управления состоит в первую очередь определение элемента и назначение ему свойств. Добавление или удаление элементов списка можно сделать в любое время.  
  
### <a name="to-add-items-programmatically"></a>Чтобы программно добавить элементы  
  
1.  Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Чтобы удалить элементы программными средствами  
  
1.  Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство. <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> Метод удаляет один элемент; <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод удаляет все элементы из списка.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
