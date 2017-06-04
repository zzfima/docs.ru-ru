---
title: "Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], переупорядочение"
  - "таблицы данных, переупорядочение столбцов"
  - "DataGridView - элемент управления [Windows Forms], порядок столбцов"
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Разрешение переупорядочивания столбцов элемента управления DataGridView в Windows Forms
При разрешении изменения порядка столбцов в элементе управления <xref:System.Windows.Forms.DataGridView> пользователи могут переместить столбец в новое местоположение, перетащив заголовок столбца с помощью мыши.  В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> определяет, могут ли пользователи перемещать столбцы.  
  
 В Visual Studio предусмотрена поддержка этой задачи.  См. также [Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\)).  
  
### Разрешение изменения порядка столбцов программным путем  
  
-   Задайте для свойства <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Практическое руководство. Замораживание столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)