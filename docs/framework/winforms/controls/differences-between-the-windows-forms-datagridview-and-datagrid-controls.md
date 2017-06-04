---
title: "Различия элементов управления DataGridView и DataGrid в Windows Forms | Microsoft Docs"
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
  - "таблицы данных"
  - "DataGrid - элемент управления [Windows Forms], сравнение элемента управления DataGridView"
  - "DataGridView - элемент управления [Windows Forms], сравнение элемента управления DataGrid"
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Различия элементов управления DataGridView и DataGrid в Windows Forms
Элемента управления <xref:System.Windows.Forms.DataGridView> — новый элемент управления, используемый вместо <xref:System.Windows.Forms.DataGrid>.  Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает ряд простых и сложных функций, отсутствующих в элементе управления <xref:System.Windows.Forms.DataGrid>.  Кроме того, архитектура элемента управления <xref:System.Windows.Forms.DataGridView> упрощает его расширение и настройку по сравнению с <xref:System.Windows.Forms.DataGrid>.  
  
 В следующей таблице описаны некоторые основные функции элемента управления <xref:System.Windows.Forms.DataGridView>, отсутствующие в <xref:System.Windows.Forms.DataGrid>.  
  
|Функция элемента управления DataGridView|Описание|  
|----------------------------------------------|--------------|  
|Различные типы столбцов|Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает больше встроенных типов столбцов, чем <xref:System.Windows.Forms.DataGrid>.  Типы столбцов соответствуют наиболее распространенным сценариям, кроме того, их легче расширять или заменять, чем в <xref:System.Windows.Forms.DataGrid>.  Дополнительные сведения см. в разделе [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Различные способы отображения данных|Элемент управления <xref:System.Windows.Forms.DataGrid> используется для отображения данных только из внешних источников.  Однако элемент управления <xref:System.Windows.Forms.DataGridView> может отображать данные, хранящиеся в самом элементе управления и не связанные ни с каким источником данных; данные из связанного источника данных, а также связанные и несвязанные данные вместе.  Также в <xref:System.Windows.Forms.DataGridView> можно реализовать виртуальный режим для управления данными.  Дополнительные сведения см. в разделе [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Различные способы настройки отображения данных|У элемента управления <xref:System.Windows.Forms.DataGridView> есть множество свойств и событий, позволяющих описать форматирование и отображение данных.  Например, можно изменить внешний вид ячеек, строк и столбцов в зависимости от содержащихся в них данных, можно заменить данные одного типа аналогичными данными другого типа.  Дополнительные сведения см. в разделе [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Различные возможности изменения внешнего вида и поведения ячеек, строк, столбцов и заголовков|Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет работать с отдельными компонентами таблицы различными способами.  Например, можно закреплять строки и столбцы, чтобы они не прокручивались; скрывать строки, столбцы и заголовки; изменять способы регулировки размера строк, столбцов и заголовков; изменить способ выделения данных пользователем, а также предоставить всплывающие подсказки и контекстные меню для отдельных ячеек, строк и столбцов.|  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в определенных случаях.  Почли для всех целей следует использовать элемент управления <xref:System.Windows.Forms.DataGridView>.  Единственная функция, доступная в элементе управления <xref:System.Windows.Forms.DataGrid> и недоступная в <xref:System.Windows.Forms.DataGridView> — иерархическое отображение данных из двух связанных таблиц в едином элементе управления.  Для отображения данных из двух связанных таблиц требуется два элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
## Обновление до элемента управления DataGridView  
 Ели в приложениях используется элемент управления <xref:System.Windows.Forms.DataGrid> в простых сценариях с привязкой к данным и без изменений, можно просто заменить старый элемент управления новым.  Оба элемента управления используют стандартную архитектуру привязки данных Windows Forms, поэтому элемент управления <xref:System.Windows.Forms.DataGridView> будет отображать связанные данные без дополнительной настройки.  Также можно воспользоваться усовершенствованиями в области привязки данных, например путем привязки данных к компоненту <xref:System.Windows.Forms.BindingSource>, который можно привязать к элементу управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения см. в разделе [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 У элемента управления <xref:System.Windows.Forms.DataGridView> совершенно новая архитектура, поэтому не существует простого и однозначного способа использовать настройки элемента управления <xref:System.Windows.Forms.DataGrid> в <xref:System.Windows.Forms.DataGridView>.  Впрочем, многие настройки <xref:System.Windows.Forms.DataGrid> являются ненужными для <xref:System.Windows.Forms.DataGridView> из\-за широкого набора встроенных функций нового элемента управления.  Если для <xref:System.Windows.Forms.DataGrid> были созданы пользовательские типы столбцов, которые нужно использовать в <xref:System.Windows.Forms.DataGridView>, их придется реализовать снова с помощью новой архитектуры.  Дополнительные сведения см. в разделе [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Windows.Forms.BindingSource>   
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Изменение размеров управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)   
 [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)   
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)