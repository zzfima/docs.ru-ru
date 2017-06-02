---
title: "Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, столбцы только для чтения"
  - "DataGridView - элемент управления [Windows Forms], столбцы только для чтения"
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms
Не все данные допускается изменять.  В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> столбца определяет, могут ли пользователи редактировать ячейки в этом столбце.  Информацию о том, как сделать весь элемент управления доступным только для чтения, см. в разделе [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).  
  
 Эта задача поддерживается в Visual Studio.  См. также [Практическое руководство. Предоставление доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).  
  
### Программное определение столбца как доступного только для чтения  
  
-   Задайте свойству <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1` и столбцом с именем `CompanyName`;  
  
-   ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)