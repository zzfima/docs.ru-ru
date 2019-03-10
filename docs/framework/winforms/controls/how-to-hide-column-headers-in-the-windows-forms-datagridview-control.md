---
title: Практическое руководство. Скрытие заголовков столбцов в элементе управления DataGridView Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: b9b78020a567d05ea000be97bb116b4f8353d56c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709462"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Скрытие заголовков столбцов в элементе управления DataGridView Windows Forms
Иногда требуется отобразить <xref:System.Windows.Forms.DataGridView> без заголовков столбцов. В <xref:System.Windows.Forms.DataGridView> элемента управления, <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> значение свойства определяет, отображаются ли заголовки столбцов.  
  
### <a name="to-hide-the-column-headers"></a>Чтобы скрыть заголовки столбцов  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> значение `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
