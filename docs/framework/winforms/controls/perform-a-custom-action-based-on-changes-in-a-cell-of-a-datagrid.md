---
title: "Практическое руководство. Выполнение пользовательских действий в ответ на изменение состояния ячеек элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, обнаружение изменений"
  - "таблицы данных, обнаружение изменений в ячейках"
  - "DataGridView - элемент управления [Windows Forms], обнаружение изменений в ячейках"
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Выполнение пользовательских действий в ответ на изменение состояния ячеек элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> имеет ряд событий, которые можно использовать для обнаружения изменений в состоянии ячеек элемента управления <xref:System.Windows.Forms.DataGridView>.  Два наиболее часто используемых события — это <xref:System.Windows.Forms.DataGridView.CellValueChanged> и <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
### Обнаружение изменений значений ячеек DataGridView  
  
-   Создайте обработчик для события <xref:System.Windows.Forms.DataGridView.CellValueChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### Обнаружение изменений состояния ячеек DataGridView  
  
-   Создайте обработчик для события <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  В C\# обработчики событий должны быть связаны с соответствующими событиями.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=fullName>   
 [Программирование с использование ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)   
 [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)