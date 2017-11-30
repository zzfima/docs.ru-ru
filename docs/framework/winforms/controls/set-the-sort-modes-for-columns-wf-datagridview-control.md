---
title: "Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a1c5b0447895b0ca5c67fff054d88da0d0107c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
В <xref:System.Windows.Forms.DataGridView> управления, столбцах текстовых полей используется автоматическая сортировка по умолчанию, а другие типы столбцов не сортируются автоматически. Иногда требуется переопределить эти значения по умолчанию. Например можно отобразить изображения вместо текста, числа или значения перечисления ячеек. Хотя нельзя выполнить сортировку изображений, можно сортировать значения, которые они представляют.  
  
 В <xref:System.Windows.Forms.DataGridView> управления, <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значение свойства столбца определяет поведение сортировки.  
  
 В следующей процедуре показан `Priority` столбец из [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Этот столбец является столбцом изображения и не поддерживает сортировку по умолчанию. Он содержит фактические значения ячеек представляют собой строки, однако, его можно сортировать по алфавиту.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Чтобы задать режим сортировки для столбца  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Priority`;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
