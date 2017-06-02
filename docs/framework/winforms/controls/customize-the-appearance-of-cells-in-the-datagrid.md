---
title: "Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ячейки, настройки в элементе управления DataGridView"
  - "таблицы данных, настройка ячеек"
  - "DataGridView - элемент управления [Windows Forms], настройка ячеек"
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms
Внешний вид ячеек может настраиваться путем обработки события <xref:System.Windows.Forms.DataGridView.CellPainting> элемента управления <xref:System.Windows.Forms.DataGridView>.  Объект <xref:System.Drawing.Graphics> элемента управления <xref:System.Windows.Forms.DataGridView> можно получить из свойства <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> объекта <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.  С помощью объекта <xref:System.Drawing.Graphics> можно изменить внешний вид всего элемента управления <xref:System.Windows.Forms.DataGridView>, однако обычно требуется изменить внешний вид только той ячейки, которая прорисовывается в данный момент.  Свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> объекта <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> позволяет ограничить применение операций рисования только к прорисовываемой в данный момент ячейке.  
  
 В следующем примере кода все ячейки столбца `ContactName` прорисовываются с использованием цветовой схемы элемента управления <xref:System.Windows.Forms.DataGridView>.  Текстовое содержимое каждой ячейки прорисовывается цветом  <xref:System.Drawing.Color.Crimson%2A>, а внутренняя рамка прорисовывается цветом, соответствующим свойству <xref:System.Windows.Forms.DataGridView.GridColor%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец `ContactName`, такой как в таблице "Customers" демонстрационной базы данных "Northwind".  
  
-   Ссылки на сборки System, System.Windows.Forms и System.Drawing.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellPainting>   
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)