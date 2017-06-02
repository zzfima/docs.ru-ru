---
title: "Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, стили строк"
  - "DataGridView - элемент управления [Windows Forms], стили строк"
  - "строки, таблицы данных"
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms
Данные в таблицах часто представлены в формате, подобном бухгалтерским книгам: в чередующихся строках используется разный цвет фона.  Такой формат позволяет проще определять, какие ячейки находятся в какой строке, что особенно удобно в широких таблицах со множеством столбцов.  
  
 С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно указать полные сведения о стиле для чередующихся строк.  Таким образом для различения чередующихся строк можно использовать такие характеристики стиля, как цвет фона, цвет текста и начертание шрифта.  
  
 Эта задача поддерживается в Visual Studio.  См. также [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/3z9sk148\(v=vs.110\)).  
  
### Задание стилей чередующихся строк программными средствами  
  
-   Задайте свойства объектов <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемых свойствами <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  Стили, заданные с помощью свойств <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>, переопределяют стили, заданные на уровне столбцов и элемента управления <xref:System.Windows.Forms.DataGridView>. Однако они, в свою очередь, переопределяются стилями, заданными на уровне отдельных строк и ячеек.  Подробнее см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Отказоустойчивость  
 Для максимальной масштабируемости объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.  Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)