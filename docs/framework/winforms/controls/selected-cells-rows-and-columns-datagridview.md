---
title: "Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "DataGridView - элемент управления [Windows Forms], получение выбранного элемента"
  - "получение выбранного элемента, DataGridView - элемент управления [Windows Forms]"
  - "выделенный фрагмент, DataGridView - элемент управления [Windows Forms]"
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms
Можно получить выделенные ячейки, строки или столбцы из элемента управления <xref:System.Windows.Forms.DataGridView> с помощью следующих свойств: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  В следующей процедуре мы получим выбранные ячейки и отобразим их индексы строк и столбцов в <xref:System.Windows.Forms.MessageBox>.  
  
### Получение выбранных ячеек в элементе управления DataGridView  
  
-   Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    >  Используйте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>, чтобы избежать отображения излишне большого числа ячеек.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### Получение выбранных строк в элементе управления DataGridView  
  
-   Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.  Чтобы дать пользователям возможность выделять строки, нужно установить свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равным <xref:System.Windows.Forms.DataGridViewSelectionMode> или <xref:System.Windows.Forms.DataGridViewSelectionMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### Получение выбранных столбцов в элементе управления DataGridView  
  
-   Используйте свойство <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  Чтобы дать пользователям возможность выделять столбцы, нужно установить свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равным <xref:System.Windows.Forms.DataGridViewSelectionMode> или <xref:System.Windows.Forms.DataGridViewSelectionMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элементы управления <xref:System.Windows.Forms.Button> с именами `selectedCellsButton`, `selectedRowsButton` и `selectedColumnsButton`, каждый с присоединенными обработчиками событий <xref:System.Windows.Forms.Control.Click>.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Text?displayProperty=fullName>.  
  
## Отказоустойчивость  
 Коллекции, описанные в этом разделе, неэффективно работают при выделении большого числа ячеек, строк или столбцов.  Дополнительные сведения об использовании этих коллекций с большими объемами данных см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>   
 [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)