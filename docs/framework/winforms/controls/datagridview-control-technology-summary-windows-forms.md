---
title: "Технологическая сводка по элементам управления DataGridView (Windows Forms) | Microsoft Docs"
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
  - "таблицы данных, сведения о таблицах данных"
  - "DataGridView - элемент управления [Windows Forms], сведения об элементе управления DataGridView"
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Технологическая сводка по элементам управления DataGridView (Windows Forms)
В этом разделе содержится сводная информация об элементе управления `DataGridView` и классах, поддерживающих его использование.  
  
 Отображение данных в табличном формате — задача, которая обычно часто выполняется.  Элемент управления `DataGridView` специально разработан как законченное решение для представления данных в виде таблицы.  
  
## Ключевые слова  
 DataGridView, BindingSource, table, cell, data binding, virtual mode, таблица, ячейка, привязка данных, виртуальный режим  
  
## Пространства имен  
 <xref:System.Windows.Forms?displayProperty=fullName>  
  
 <xref:System.Data?displayProperty=fullName>  
  
## Связанные технологии  
 `BindingSource`  
  
## Фон  
 У разработчиков пользовательского интерфейса часто возникает необходимость отображения табличных данных пользователям.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляет несколько способов отображения данных в виде таблицы или сетки.  Элемент управления `DataGridView` представляет собой новейшее развитие этой технологии для приложений Windows Forms.  
  
 Элемент управления `DataGridView` позволяет отображать строки данных, полученных из хранилища данных.  Поддерживаются различные типы хранилищ данных.  Хранилище данных может содержать как простые, нетипизированные данные \(например, одномерный массив\), так и типизированные данные \(например, <xref:System.Data.DataSet>\).  Дополнительные сведения содержатся в разделе [Практическое руководство. Привязка данных к элементу управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Элемент управления `DataGridView` предоставляет мощный и гибкий способ отображения данных в табличном формате.  Элемент управления может использоваться для отображения представлений наборов данных, доступных только для чтения, и изменяемых представлений; причем наборы данных могут быть любого объема — от малых до сверхбольших.  
  
 Функциональные возможности элемента управления `DataGridView` можно расширить несколькими способами, чтобы реализовать пользовательское поведение в приложениях.  Например, можно программно задать собственные алгоритмы сортировки, а также создать собственные типы ячеек.  Внешний вид элемента управления `DataGridView` можно настроить, задав несколько свойств.  В качестве источника данных могут использоваться различные типы хранилищ данных. Кроме того, элемент управления `DataGridView` может работать без связанных источников данных.  
  
## Реализация классов DataGridView  
 Существует несколько способов, позволяющих воспользоваться преимуществами функций расширения элемента управления `DataGridView`.  Хотя с помощью событий и свойств можно настраивать различные аспекты элемента управления, для некоторых настроек требуется создание новых классов, производных от существующих классов `DataGridView`.  
  
 Наиболее часто используются классы `DataGridViewCell` и `DataGridViewColumn`.  Собственные классы ячеек можно получить, как производные от класса `DataGridViewCell` или любого его дочернего класса.  Хотя в любой столбец можно добавить любой тип ячеек, обычно для размещения по умолчанию пользовательского типа ячеек создается сопутствующий класс столбца, производный от `DataGridViewColumn`.  
  
 Для создания типа ячеек, поддерживающего возможности редактирования, но не размещающего элемент управления в режиме редактирования, можно реализовать интерфейс `IDataGridViewEditingCell` в собственном производном классе ячеек.  Для создания элемента управления, поддерживающего размещение в ячейке в режиме редактирования, можно реализовать интерфейс `IDataGridViewEditingControl` в классе, производном от <xref:System.Windows.Forms.Control>.  
  
 Дополнительные сведения см. в разделах [Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) и [Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## Классы DataGridView на первый взгляд  
 <xref:System.Windows.Forms>  
  
|Область технологий|Classes\/interfaces\/configuration elements|  
|------------------------|-------------------------------------------------|  
|Привязка данных|<xref:System.Windows.Forms.BindingSource>|  
|Представление данных|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|Расширяемость <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## Новые возможности  
 Элемент управления <xref:System.Windows.Forms.DataGridView> специально разработан как законченное решение для представления табличных данных с помощью Windows Forms.  При создании нового приложения рассмотрите возможность использования элемента управления <xref:System.Windows.Forms.DataGridView>, прежде чем рассматривать другие решения, такие как <xref:System.Windows.Forms.DataGrid>.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> может работать в сочетании с компонентом <xref:System.Windows.Forms.BindingSource>.  Этот компонент предназначен для использования в качестве основного источника данных для формы.  Он управляет взаимодействием между элементом управления <xref:System.Windows.Forms.DataGridView> и источником данных, вне зависимости от типа источника данных.  
  
## См. также  
 [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)