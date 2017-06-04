---
title: "Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, режим редактирования"
  - "DataGridView - элемент управления [Windows Forms], режим редактирования"
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms
По умолчанию пользователи могут изменять содержимое текущей ячейки текстового поля <xref:System.Windows.Forms.DataGridView> путем набора в ней или при нажатии клавиши F2.  Ячейка переключается в режим редактирования при выполнении всех следующих условиях:  
  
-   Основной источник данных поддерживает редактирования.  
  
-   Элемента управления <xref:System.Windows.Forms.DataGridView> включен.  
  
-   Значение свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A> не равно <xref:System.Windows.Forms.DataGridViewEditMode>.  
  
-   Все свойства `ReadOnly` ячейки, строки, столбца и элемента управления имеют значение `false`.  
  
 В режиме редактирования пользователь может изменить значение ячейки и нажать клавишу ENTER для подтверждения изменений или ESC для возврата предыдущего значения ячейки.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> можно настроить таким образом, что ячейка будет переключаться в режим редактирования как только будет становиться текущей.  В этом случае поведение клавиш ENTER и ESC не изменяется, но ячейка остается в режиме редактирования после подтверждения или возврата значения.  Элемент управления можно также настроить таким образом, что ячейки будут переключаться в режим редактирования только при наборе пользователем в ячейке или только при нажатии клавиши F2.  И, наконец, переключение ячеек в режим редактирования можно запретить во всех случаях, кроме случая вызова метода <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.  
  
### Изменение режима редактирования элемента управления DataGridView  
  
-   Присвойте свойству <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName> соответствующее перечисление <xref:System.Windows.Forms.DataGridViewEditMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Ссылки на сборки <xref:System> и <xref:System.Windows.Forms>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName>   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)