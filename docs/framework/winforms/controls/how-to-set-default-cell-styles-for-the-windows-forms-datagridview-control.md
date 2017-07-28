---
title: "Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, стили"
  - "таблицы данных, стили ячеек"
  - "DataGridView - элемент управления [Windows Forms], стили ячеек"
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms
С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно задавать стили ячеек по умолчанию для всего элемента управления или для определенных столбцов и строк.  Эти стили по умолчанию отфильтровываются на уровне элемента управления, затем на уровне столбца, строки и, наконец, на уровне ячейки.  Если определенное свойство <xref:System.Windows.Forms.DataGridViewCellStyle> не задано на уровне ячейки, то на уровне строки используется свойство по умолчанию.  Если свойство не задано и на уровне строки, то используется значение столбца по умолчанию.  Наконец, если свойство не задано на уровне столбца, то по умолчанию используется значение <xref:System.Windows.Forms.DataGridView>.  Использование этой настройки позволит избежать дублирования значений свойств на нескольких уровнях.  На каждом уровне нужно просто указывать стили, отличающиеся от вышестоящих уровней.  Подробнее см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 В Visual Studio предусмотрена расширенная поддержка этой задачи.  См. также [Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).  
  
### Программная установка стилей ячейки по умолчанию  
  
1.  Задайте свойства <xref:System.Windows.Forms.DataGridViewCellStyle>, извлеченные с помощью свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  Создайте и инициализируйте новые объекты <xref:System.Windows.Forms.DataGridViewCellStyle> для использования несколькими строками и столбцами.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  Задайте свойство `DefaultCellStyle` определенных строк и столбцов.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Отказоустойчивость  
 Для максимальной масштабируемости при работе с большими наборами данных объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.  Кроме того, следует создать общие строки и обращаться к ним с помощью свойства <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName>.  Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)