---
title: "Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms"
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
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61b2a39943dfca412afa4b66265aabbf65b9ccf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms
Можно настроить внешний вид ячеек, обрабатывая <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.CellPainting> событий. Можно извлечь <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Drawing.Graphics> из <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. С этим <xref:System.Drawing.Graphics>, могут повлиять на внешний вид всего <xref:System.Windows.Forms.DataGridView> элемент управления, но обычно нужно повлияют на вид в настоящее время закрашиваемой ячейки. <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> позволяет ограничить применение операций рисования в в настоящее время, содержащей закрашиваемую ячейку.  
  
 В следующем примере кода будет отрисовываться все ячейки в `ContactName` столбца с помощью <xref:System.Windows.Forms.DataGridView> цветовой схемы элемента управления. Текстовое содержимое каждой ячейки, рисуется в <xref:System.Drawing.Color.Crimson%2A>, и в тот же цвет, что рисуется внутренняя рамка <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.GridColor%2A> свойство.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Объект <xref:System.Windows.Forms.DataGridView> управления с именем `dataGridView1` с `ContactName` столбца, подобное показанному в таблице Customers в учебной базе данных Northwind.  
  
-   ссылки на сборки System, System.Windows.Forms и System.Drawing.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
