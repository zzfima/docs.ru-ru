---
title: "Практическое руководство. Сокрытие заголовков столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "заголовки столбцов, скрытие"
  - "столбцы [Windows Forms], скрытие заголовков столбцов"
  - "DataGridView - элемент управления [Windows Forms], заголовки столбцов"
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Сокрытие заголовков столбцов элемента управления DataGridView в Windows Forms
Иногда требуется отобразить элемент управления <xref:System.Windows.Forms.DataGridView> без заголовков столбцов.  Отображение заголовков столбцов в элементе управления <xref:System.Windows.Forms.DataGridView>, определяется значением свойства <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>.  
  
### Сокрытие заголовков столбцов  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName> значение `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)