---
title: Скрытие заголовков столбцов в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: d84c93b0ad1c9ef456c73dd29af1de4857778999
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736593"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Сокрытие заголовков столбцов элемента управления DataGridView в Windows Forms
Иногда может потребоваться отобразить <xref:System.Windows.Forms.DataGridView> без заголовков столбцов. В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> определяет, отображаются ли заголовки столбцов.  
  
### <a name="to-hide-the-column-headers"></a>Скрытие заголовков столбцов  
  
- Установите свойство <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> в значение `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
