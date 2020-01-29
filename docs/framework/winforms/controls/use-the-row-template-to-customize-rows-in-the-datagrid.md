---
title: Использование шаблона строк для настройки строк в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 35cb95f22c0caa654bf149b5fc4fd0395696a411
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728381"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> использует шаблон строк в качестве основания для всех строк, добавляемых в элемент управления с помощью привязки данных, или при вызове метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> без указания существующей строки для использования.  
  
 Шаблон строки обеспечивает больший контроль над внешним видом и поведением строк, чем предоставляет свойство <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>. С помощью шаблона строки можно задать любые свойства <xref:System.Windows.Forms.DataGridViewRow>, в том числе <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Существует несколько ситуаций, в которых для достижения определенного результата необходимо использовать шаблон строки. Например, сведения о высоте строки не могут храниться в <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому для изменения высоты по умолчанию, используемой всеми строками, необходимо использовать шаблон строк. Шаблон строки также полезен при создании собственных классов, производных от <xref:System.Windows.Forms.DataGridViewRow> и необходимости использовать пользовательский тип при добавлении новых строк к элементу управления.  
  
> [!NOTE]
> Шаблон строки используется только при добавлении строк. Нельзя изменить существующие строки, изменив шаблон строки.  
  
### <a name="to-use-the-row-template"></a>Использование шаблона строки  
  
- Задайте свойства объекта, полученного из свойства <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
