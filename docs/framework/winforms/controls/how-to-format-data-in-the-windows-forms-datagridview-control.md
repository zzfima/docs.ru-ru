---
title: "Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, выравнивание текста"
  - "значения валют, форматирование в таблицах данных"
  - "данные [Windows Forms], форматирование данных в элементе управления DataGridView"
  - "таблицы данных, значения валют"
  - "таблицы данных, значения даты"
  - "таблицы данных, включение переноса слов"
  - "таблицы данных, форматирование данных"
  - "таблицы данных, выравнивание текста"
  - "DataGridView - элемент управления [Windows Forms], форматирование данных"
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms
Следующие процедуры демонстрируют основные способы форматирования значений ячеек с помощью свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView>, а также форматирование определенных столбцов элемента управления.  Сведения о расширенных возможностях форматирования данных см. в разделе [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### Форматирование значений даты и валюты  
  
-   Задайте значение свойства <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.  В следующем примере кода устанавливается формат определенных столбцов с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> столбцов.  Значения столбца `UnitPrice` отображаются в текущем формате валюты, принятом для данной страны, причем отрицательные значения заключаются в круглые скобки.  Значения столбца `ShipDate` отображаются в текущем кратком формате даты, принятом для данной страны.  Дополнительные сведения о значениях свойства <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> см. в разделе [Типы форматирования](../../../../docs/standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### Настройка отображения пустых значений базы данных  
  
-   Задайте значение свойства <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.  В следующем примере кода свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> используется для отображения значения "no entry" \(пустая запись\) во всех ячейках, имеющих значение <xref:System.DBNull.Value?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### Включение переноса слов в текстовых ячейках  
  
-   Присвойте свойству <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle> одно из значений перечисления <xref:System.Windows.Forms.DataGridViewTriState>.  В следующем примере кода свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> используется для задания режима переноса для всего элемента управления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### Указание способа выравнивания текста для ячеек элемента управления DataGridView  
  
-   Присвойте свойству <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle> одно из значений перечисления <xref:System.Windows.Forms.DataGridViewContentAlignment>.  В следующем примере кода устанавливается способ выравнивания для определенного столбца с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> данного столбца.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## Компиляция кода  
 Для выполнения данных примеров требуются следующие компоненты:  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбцы с именами `UnitPrice`, `ShipDate` и `CustomerName`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Отказоустойчивость  
 Для достижения максимальной масштабируемости, объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.  Дополнительные сведения см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Типы форматирования](../../../../docs/standard/base-types/formatting-types.md)