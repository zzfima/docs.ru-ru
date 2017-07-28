---
title: "Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, получение и задание текущего"
  - "DataGridView - элемент управления [Windows Forms], получение текущей ячейки"
  - "DataGridView - элемент управления [Windows Forms], установка текущей ячейки"
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms
Взаимодействие с элементом <xref:System.Windows.Forms.DataGridView> часто требует определения текущей активной ячейки программным способом.  Может также потребоваться изменить текущую ячейку.  Эти задачи можно выполнить с помощью свойства <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>.  
  
> [!NOTE]
>  Нельзя настроить текущую ячейку в строке или столбце, если ее свойство <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> имеет значение `false`.  
  
 В зависимости от режима выбора элемента управления <xref:System.Windows.Forms.DataGridView> изменение текущей ячейки может изменить выбор.  Дополнительные сведения см. в разделе [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### Чтобы получить текущую ячейку программным путем, выполните следующие действия:  
  
-   Используйте свойство <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### Чтобы настроить текущую ячейку программным путем, выполните следующие действия:  
  
-   Задайте нужное значение для свойства <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  В приведенном ниже примере кода текущая ячейка находится в строке 0 и столбце 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элементы управления <xref:System.Windows.Forms.Button> с именами `getCurrentCellButton` и `setCurrentCellButton`.  В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] необходимо связать события <xref:System.Windows.Forms.Control.Click> для каждой кнопки с соответствующим обработчиком событий в коде примера.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=fullName>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)