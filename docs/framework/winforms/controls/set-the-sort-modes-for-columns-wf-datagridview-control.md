---
title: "Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, сортировка данных"
  - "DataGridView - элемент управления [Windows Forms], режим сортировки"
  - "сортировка, таблицы данных"
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
В элементе управления <xref:System.Windows.Forms.DataGridView> в столбцах текстовых полей по умолчанию используется автоматическая сортировка, а другие типы столбцов не имеют автоматической сортировки.  Иногда нужно заменить значения по умолчанию.  Например, можно отображать рисунки вместо текста, числа или значения номеров ячеек.  Сортировка рисунков невозможно, но можно сортировать значения, которые представлены рисунками.  
  
 В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> столбца определяет поведение сортировки.  
  
 В следующей процедуре показан столбец `Priority` из [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  Этот столбец содержит рисунки, которые по умолчанию не сортируются.  Однако фактические значения ячеек — строки, поэтому их можно сортировать по алфавиту.  
  
### Для установки режима сортировки для столбца выполните следующие действия.  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `Priority`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)