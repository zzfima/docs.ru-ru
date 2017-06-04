---
title: "Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, изменение стиля границы"
  - "таблицы данных, изменение стиля сетки"
  - "DataGridView - элемент управления [Windows Forms], стили границ"
  - "DataGridView - элемент управления [Windows Forms], стили сетки"
  - "линии сетки, изменение стилей"
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет изменять внешний вид границы и линий сетки элемента управления для более удобной работы пользователя.  Помимо стилей границ ячеек, в элементе управления можно также изменить цвет границ и определить их стиль.  Кроме того, к обычным ячейкам, ячейкам заголовка строки и ячейкам заголовка столбца можно применить различные стили границ.  
  
> [!NOTE]
>  Цвета линий сетки используются только с <xref:System.Windows.Forms.DataGridViewCellBorderStyle>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle> и значениями <xref:System.Windows.Forms.DataGridViewCellBorderStyle> перечисления <xref:System.Windows.Forms.DataGridViewCellBorderStyle>, а также значением <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> перечисления <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>.  Другие значения этих перечислений используют цвета, задаваемые операционной системой.  Кроме того, при включении визуальных стилей операционных систем Windows XP и Windows Server 2003 при помощи метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>, значение свойства <xref:System.Windows.Forms.DataGridView.GridColor%2A> не используется.  
  
### Изменение цвета линий сетки программным образом  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridView.GridColor%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### Изменение стиля границ всего элемента управления DataGridView программным способом  
  
-   Присвойте свойству <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> одно из значений перечисления <xref:System.Windows.Forms.BorderStyle>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### Изменение стилей границ для ячеек DataGridView программным способом  
  
-   Установите свойства <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A> и <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Drawing?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.BorderStyle>   
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>   
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)