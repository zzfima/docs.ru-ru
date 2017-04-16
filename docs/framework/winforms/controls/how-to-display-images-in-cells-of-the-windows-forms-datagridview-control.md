---
title: "Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, отображение изображений"
  - "таблицы данных, отображение изображений в ячейках"
  - "таблицы данных, отображение в таблице"
  - "DataGridView - элемент управления [Windows Forms], отображение изображений"
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms
Рисунок или изображение — одно из значений, которое можно отображать в строке данных.  Как правило эти изображения представляют собой фотографии сотрудников или эмблему компании.  
  
 Применение рисунков очень просто при отображении данных в элементе управления <xref:System.Windows.Forms.DataGridView>.  Элемент управления <xref:System.Windows.Forms.DataGridView> изначально может обрабатывать рисунки любого формата, поддерживаемого классом <xref:System.Drawing.Image>, а также рисунки формата OLE, используемого в некоторых базах данных.  
  
 Если источник данных элемента управления <xref:System.Windows.Forms.DataGridView> имеет столбец рисунков, они будут автоматически отображаться элементом управления <xref:System.Windows.Forms.DataGridView>.  
  
 Следующий код демонстрирует извлечение значка из встроенного ресурса и его преобразование в растровый рисунок для отображения во всех ячейках столбца рисунков.  Другой пример, в котором текстовые значения ячеек заменяются рисунками, см. в разделе [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ресурс со встроенным значком с именем `tree.ico`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Drawing?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)