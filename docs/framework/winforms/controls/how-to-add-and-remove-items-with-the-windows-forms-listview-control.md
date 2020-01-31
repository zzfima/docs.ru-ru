---
title: Добавление и удаление элементов с помощью элемента управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743138"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> состоит главным образом из указания элемента и присвоения ему свойств. Добавление или удаление элементов списка можно выполнить в любое время.  
  
### <a name="to-add-items-programmatically"></a>Добавление элементов программным способом  
  
1. Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Удаление элементов программным способом  
  
1. Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>. Метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> удаляет один элемент. метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> удаляет все элементы из списка.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
