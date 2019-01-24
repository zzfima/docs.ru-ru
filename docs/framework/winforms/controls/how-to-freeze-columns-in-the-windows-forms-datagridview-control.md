---
title: Как выполнить Закрепление столбцов в элементе управления DataGridView Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: b7a657af2d6caf2217aedf56422f135f0b2d667e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619425"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a>Как выполнить Закрепление столбцов в элементе управления DataGridView Windows Forms
При просмотре пользователями данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, им порой требуется часто обращаться к одному столбцу или набору столбцов. Например, при просмотре таблицы сведений о пользователе, содержащей много столбцов, может быть желательно, чтобы имя пользователя отображалось постоянно при прокручивании остальных столбцов за пределы видимости.  
  
 Для этого необходимо закрепить столбцы в элементе управления. При закреплении столбца все столбцы слева от него (или справа для языков с направлением письма справа налево) также закрепляются. Закрепленные столбцы остаются на месте в то время, как остальные столбцы можно прокручивать.  
  
> [!NOTE]
>  Если разрешено переупорядочивание столбцов, закрепленные столбцы рассматриваются как группа, отличная от группы незакрепленных столбцов. Пользователи могут переставлять местами столбцы в каждой из групп, но не могут перемещать столбцы из одной группы в другую.  
  
 Свойство <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> столбца определяет, должен ли он отображаться в сетке постоянно.  
  
 Эта задача поддерживается в Visual Studio.  Также см. раздел [Как Замораживание столбцов в Windows Forms с помощью конструктора элемента управления DataGridView](https://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).  
  
### <a name="to-freeze-a-column-programmatically"></a>Программное закрепление столбца  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `AddToCartButton`;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Практическое руководство. Разрешение изменения порядка столбцов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
