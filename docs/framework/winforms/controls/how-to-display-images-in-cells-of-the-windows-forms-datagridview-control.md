---
title: Отображение изображений в ячейках элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740286"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms
Изображение или рисунок — это одно из значений, которое можно отобразить в строке данных. Часто эти графические изображения имеют форму фотографии сотрудника или логотипа компании.  
  
 Внедрение рисунков выполняется просто при отображении данных в элементе управления <xref:System.Windows.Forms.DataGridView>. Элемент управления <xref:System.Windows.Forms.DataGridView> изначально обрабатывает любой формат изображения, поддерживаемый классом <xref:System.Drawing.Image>, а также формат изображения OLE, используемый некоторыми базами данных.  
  
 Если источник данных элемента управления <xref:System.Windows.Forms.DataGridView> имеет столбец изображений, они будут автоматически отображаться элементом управления <xref:System.Windows.Forms.DataGridView>.  
  
 В следующем примере кода показано, как извлечь значок из внедренного ресурса и преобразовать его в точечный рисунок для отображения в каждой ячейке столбца Image. Другой пример, в котором текстовые значения ячеек заменяются соответствующими изображениями, см. в разделе [как настроить форматирование данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- Внедренный ресурс значка с именем `tree.ico`.  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
