---
title: Элементы группы в управлении ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141995"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms
С функцией группировки <xref:System.Windows.Forms.ListView> элемента управления можно отображать связанные наборы элементов в группах. Эти группы разделены на экране горизонтальными заголовками групп, содержащими названия групп. Группы <xref:System.Windows.Forms.ListView> можно использовать для облегчения навигации по большим спискам, группируя элементы в алфавитном порядке, по дате или по любой другой логической группировке. На следующем изображении показаны некоторые сгруппированные элементы.  
  
 ![Скриншот нечетных и четных групп ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 Для обеспечения группировки необходимо сначала создать одну или несколько групп в составе дизайнера или в программном плане. После определения группы можно назначить <xref:System.Windows.Forms.ListView> элементы группам. Вы также можете перемещать элементы из одной группы в другую в программном плане.  
  
### <a name="to-add-groups"></a>Добавление групп  
  
1. Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Удаление групп  
  
1. Используйте <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> или метод <xref:System.Windows.Forms.ListView.Groups%2A> сбора.  
  
     Метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> удаляет одну группу; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> метод удаляет все группы из списка.  
  
    > [!NOTE]
    > Удаление группы не удаляет элементы в этой группе.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Назначать элементы группам или перемещать элементы между группами  
  
1. Установите <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> свойство отдельных элементов.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
