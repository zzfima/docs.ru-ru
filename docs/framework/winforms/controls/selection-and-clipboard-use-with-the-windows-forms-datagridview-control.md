---
title: "Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, выбор в сетке"
  - "буфер обмена, в элементе управления DataGridView"
  - "таблицы данных, выбор ячеек"
  - "DataGridView - элемент управления [Windows Forms], использование буфера обмена"
  - "DataGridView - элемент управления [Windows Forms], выбор ячеек"
  - "выделенный фрагмент, в элементе управления DataGridView"
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms
Элемент управления `DataGridView` имеет множество параметров, позволяющих настроить выбор пользователем ячеек, строк и столбцов.  Например, можно разрешить выбор одного или нескольких элементов, выбор целых строк или столбцов, в которых пользователь щелкнул ячейки, или выбор целых строк или столбцов только, если пользователь щелкнул их заголовки, что также разрешает выбор ячейки.  Если необходимо настроить собственный пользовательский интерфейс для функций выбора, то можно отключить стандартные функции выбора и обрабатывать все команды выбора программным путем.  Кроме того, можно разрешить пользователям копировать выбранные значения в буфер обмена.  
  
## В этом подразделе  
 [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 Описание параметров пользовательских и программных функций выбора в элементе управления.  
  
 [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 Описание настройки элемента управления на выбор одной строки при щелчке ячейки.  
  
 [Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 Описание работы с выбранными коллекциями ячеек, строк и столбцов.  
  
 [Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 Описание включения поддержки буфера обмена в элементе управления.  
  
## Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>  
 Справочная документация по свойству <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>.  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 Справочная документация по свойству <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 Справочная документация по классу <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 Справочная документация по классу <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 Справочная документация по классу <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>.  
  
## См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)