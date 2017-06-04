---
title: "Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, настройка строк"
  - "DataGridView - элемент управления [Windows Forms], настройка строк"
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms
Шаблон строк используется элементом управления <xref:System.Windows.Forms.DataGridView> в качестве образца для всех строк, добавляемых в элемент управления путем привязки данных или при вызове метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName> без указания существующей строки.  
  
 Шаблон строк обеспечивает более широкие возможности управления внешним видом и поведением строк по сравнению со свойством <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.  С помощью шаблона строк можно задать любые свойства <xref:System.Windows.Forms.DataGridViewRow>, включая <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 В некоторых ситуациях для достижения определенного результата использование шаблонов строк является необходимым.  Например, информацию о высоте строки нельзя сохранить в свойстве <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому для изменения высоты, принимаемой по умолчанию для всех строк, необходимо использовать шаблон строк.  Шаблоны строк могут использоваться также при создании собственных классов, производных от <xref:System.Windows.Forms.DataGridViewRow>, если пользовательский тип предполагается использовать впоследствии при добавлении новых строк в элемент управления.  
  
> [!NOTE]
>  Шаблон строк используется только при добавлении строк.  Существующие строки невозможно изменить путем настройки шаблона строк.  
  
### Использование шаблона строк  
  
-   Задайте свойства объекта, полученного из свойства <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridViewRow>   
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)