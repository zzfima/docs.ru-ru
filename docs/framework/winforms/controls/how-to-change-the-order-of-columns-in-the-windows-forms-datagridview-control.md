---
title: Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: a8e18080e757ceb4818bb795926a1eb4c27cf067
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583359"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms
При использовании <xref:System.Windows.Forms.DataGridView> для отображения данных из источника данных столбцы в схеме данных не всегда выводятся в нужном порядке. Порядок отображения столбцов можно изменить с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> класса <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 В примере кода ниже изменяется положение некоторых столбцов, автоматически созданных при привязке к таблице Customers в базе данных Northwind. Дополнительные сведения о том, как привязать <xref:System.Windows.Forms.DataGridView> управления с таблицей базы данных, см. в разделе [как: Привязка данных к Windows Forms элемента управления DataGridView](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Эта задача поддерживается в Visual Studio.  Также см. раздел [Как Изменить порядок столбцов в элементе управления DataGridView формы Windows с помощью конструктора](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `customersDataGridView`, связанный с таблицей с указанными именами столбцов, например с таблицей `Customers` базы данных Northwind;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> и <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Привязка данных к элементу управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)
