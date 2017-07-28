---
title: "Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, стили цвета"
  - "таблицы данных, настройка ячеек"
  - "таблицы данных, стили шрифтов"
  - "DataGridView - элемент управления [Windows Forms], настройка ячеек"
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms
Внешний вид ячеек в элементе управления <xref:System.Windows.Forms.DataGridView> можно определять путем указания свойств класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  Экземпляры этого класса можно извлечь из различных свойств класса <xref:System.Windows.Forms.DataGridView> и сопутствующих классов или же можно создать экземпляры объектов <xref:System.Windows.Forms.DataGridViewCellStyle> для назначения этим свойствам.  
  
 Приведенные ниже процедуры демонстрируют основные способы настройки внешнего вида ячеек с помощью свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>.  Каждая ячейка элемента управления наследует стили, указанные с помощью этого свойства, если они не переопределены на уровне столбца, строки или ячейки.  Пример наследования стиля см. в разделе [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Информацию о дополнительных способах использования класса <xref:System.Windows.Forms.DataGridViewCellStyle> см. в разделах, перечисленных в разделе "См. также".  
  
 В Visual Studio предусмотрена расширенная поддержка этой задачи.  См. также [Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).  
  
### Указание шрифта текста для ячеек элемента управления DataGridView  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.  В примере кода ниже свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> используется для задания шрифта для всего элемента управления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### Указание цветов текста и фона для ячеек элемента управления DataGridView  
  
-   Задайте свойства <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.  В примере кода ниже свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> используется с целью задания стилей для всего элемента управления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### Указание цветов текста и фона для выбранных ячеек элемента управления DataGridView  
  
-   Задайте свойства <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.  В примере кода ниже свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> используется с целью задания стилей для всего элемента управления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Отказоустойчивость  
 Для максимальной масштабируемости объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.  Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)