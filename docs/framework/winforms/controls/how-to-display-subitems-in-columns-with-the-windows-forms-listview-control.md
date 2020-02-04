---
title: Отображение подэлементов в столбцах с помощью элемента управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745544"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.ListView> может отображать дополнительный текст или подэлементы для каждого элемента в представлении сведений. В первом столбце отображается текст элемента, например номер сотрудника. Во втором, третьем и последующих столбцах отображаются первый, второй и последующие связанные подэлементы.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Добавление подэлементов в элемент списка  
  
1. Добавьте необходимые столбцы. Поскольку в первом столбце отображается свойство <xref:System.Windows.Forms.ListView.Text%2A> элемента, требуется еще один столбец, чем количество подэлементов. Дополнительные сведения о добавлении столбцов см. в разделе [инструкции. Добавление столбцов в Windows Forms элемент управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2. Вызовите метод <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> коллекции, возвращенной свойством <xref:System.Windows.Forms.ListViewItem.SubItems%2A> элемента. В приведенном ниже примере кода задается имя сотрудника и отдел для элемента списка.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
