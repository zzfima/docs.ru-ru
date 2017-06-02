---
title: "Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "таблицы данных, добавление всплывающих подсказок"
  - "DataGridView - элемент управления [Windows Forms], добавление всплывающих подсказок"
  - "всплывающие подсказки [Windows Forms], добавление в таблицу данных"
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Определение текста всплывающих подсказок для отдельных ячеек элемента управления DataGridView в Windows Forms
По умолчанию всплывающие подсказки используются для отображения значений ячеек <xref:System.Windows.Forms.DataGridView>, размер которых не позволяет отображать их полное содержимое.  Однако, это поведение можно переопределить, задав текстовые значения всплывающих подсказок для отдельных ячеек.  Это полезно для отображения дополнительных сведений пользователям о ячейке или предоставления пользователям дополнительного описания о содержимом ячейки.  Например, в строку, отображающую значки состояния, может потребоваться включение текстовых пояснений по использованию всплывающих подсказок.  
  
 Отображение всплывающих подсказок на уровне ячейки можно также отключить, присвоив свойству <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName> значение `false`.  
  
### Добавление всплывающей подсказки в ячейку  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## Компиляция кода  
  
-   Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Rating` для отображения строковых значений, состоящих из символов звездочки \("\*"\) \(от одного до четырех\).  Событие <xref:System.Windows.Forms.DataGridView.CellFormatting> элемента управления должно быть связано с методом обработчика событий, показанным в примере.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Отказоустойчивость  
 При привязке элемента управления <xref:System.Windows.Forms.DataGridView> к к внешнему источнику данных или предоставлении собственного источника данных путем реализации виртуального режима могут возникнуть проблемы производительности.  Чтобы избежать потери производительности при работе с большими объемами данных, рекомендуется использовать событие <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> вместо задания свойства <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> нескольких ячеек.  При обработке этого события, получение свойства <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> ячейки вызывает событие и возвращает значение свойства <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=fullName>, указанного в обработчике событий.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>   
 [Программирование с использование ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)