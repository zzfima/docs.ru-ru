---
title: "Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms"
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
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56c8558f34c895567c3eebfbb5a89612c4b56224
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms
Рисунок или изображение — одно из значений, которые могут быть отображены в строке данных. Как правило эти графики принимать форму фотография сотрудника или логотип компании.  
  
 Применение рисунков очень просто, при отображении данных в пределах <xref:System.Windows.Forms.DataGridView> элемента управления. <xref:System.Windows.Forms.DataGridView> Управления изначально может обрабатывать любой поддерживаемый формат изображения <xref:System.Drawing.Image> класса, а также OLE рисунка формат, используемый в некоторых базах данных.  
  
 Если <xref:System.Windows.Forms.DataGridView> элемента управления источника данных есть столбец изображения, они будут автоматически отображаться элементом <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 В следующем примере кода показано, как для извлечения значка из внедренного ресурса и его преобразования в растровое изображение для отображения во всех ячейках столбца изображений. Другой пример, в котором текстовые значения ячеек заменяются рисунками, см. [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   Ресурс со встроенным значком с именем `tree.ico`.  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
