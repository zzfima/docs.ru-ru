---
title: Группирование элементов в элементе управления ListView
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736624"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms
Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать связанные наборы элементов в группах. Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп. Вы можете использовать группы <xref:System.Windows.Forms.ListView>, чтобы упростить навигацию по большим спискам, группируя элементы по алфавиту, по датам или по любой другой логической группировке. На следующем рисунке показаны некоторые сгруппированные элементы.  
  
 ![Снимок экрана с четными и даже группами ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 Чтобы включить группирование, необходимо сначала создать одну или несколько групп либо в конструкторе, либо программно. После определения группы можно назначить элементы <xref:System.Windows.Forms.ListView> группам. Можно также перемещать элементы из одной группы в другую программным способом.  
  
### <a name="to-add-groups"></a>Добавление групп  
  
1. Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Удаление групп  
  
1. Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     Метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> удаляет одну группу; метод <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> удаляет все группы из списка.  
  
    > [!NOTE]
    > При удалении группы элементы в этой группе не удаляются.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Назначение элементов группам или перемещение элементов между группами  
  
1. Задайте свойство <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> отдельных элементов.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
