---
title: Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966495"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms
Элемент управления использует шаблон строк в качестве основания для всех строк, добавляемых в элемент управления с помощью привязки данных, или при <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> вызове метода без указания существующей строки для использования. <xref:System.Windows.Forms.DataGridView>  
  
 Шаблон строки обеспечивает больший контроль над внешним видом и поведением строк, чем <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> предоставляет свойство. С помощью шаблона строки можно задать любые <xref:System.Windows.Forms.DataGridViewRow> свойства, включая. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>  
  
 Существует несколько ситуаций, в которых для достижения определенного результата необходимо использовать шаблон строки. Например, сведения о высоте строки не могут храниться в <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому для изменения высоты по умолчанию, используемой всеми строками, необходимо использовать шаблон строк. Шаблон строки также полезен при создании собственных классов, производных от <xref:System.Windows.Forms.DataGridViewRow> , и необходимости использовать пользовательский тип при добавлении новых строк к элементу управления.  
  
> [!NOTE]
> Шаблон строки используется только при добавлении строк. Нельзя изменить существующие строки, изменив шаблон строки.  
  
### <a name="to-use-the-row-template"></a>Использование шаблона строки  
  
- Задайте свойства объекта, полученного из <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> свойства.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
