---
title: "Общие сведения об элементе управления DataGridView (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGridView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления с привязкой, DataGridView - элемент управления"
  - "столбцы [Windows Forms], DataGridView - элемент управления"
  - "данные [Windows Forms], переходы"
  - "данные [Windows Forms], повторная сортировка"
  - "привязка данных, DataGridView - элемент управления"
  - "таблицы данных, сведения о таблицах данных"
  - "источники данных, привязка данных к элементу управления DataGridView"
  - "DataGridView - элемент управления [Windows Forms], сведения об элементе управления DataGridView"
  - "DataGridView - элемент управления [Windows Forms], привязка данных"
  - "наборы данных [Windows Forms], привязка данных к элементу управления DataGridView"
  - "элементы управления [Windows Forms]"
  - "сетки [Windows Forms]"
  - "таблицы [Windows Forms], привязка данных к элементу управления DataGridView"
  - "таблицы [Windows Forms], отображение данных в элементе управления DataGridView"
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Общие сведения об элементе управления DataGridView (Windows Forms)
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет отображать и редактировать табличные данные из различных типов источников данных.  
  
 Связывание данных с элементом управления <xref:System.Windows.Forms.DataGridView> — интуитивно понятная и простая процедура, которая в большинстве случаев не сложнее установки свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A>.  При привязке к источнику данных, содержащим несколько списков или таблиц, в качестве значения свойства <xref:System.Windows.Forms.DataGridView.DataMember%2A> необходимо задать строку, указывающую таблицу или список для привязки.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную модель привязки данных Windows Form, допускающую привязку к экземплярам классов, описание которых приведено в следующем списке.  
  
-   Любой класс, реализующий интерфейс <xref:System.Collections.IList>, включая одномерные массивы.  
  
-   Любой класс, реализующий интерфейс <xref:System.ComponentModel.IListSource>, например классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet>.  
  
-   Любой класс, реализующий интерфейс <xref:System.ComponentModel.IBindingList>, например класс <xref:System.ComponentModel.BindingList%601>.  
  
-   Любой класс, реализующий интерфейс <xref:System.ComponentModel.IBindingListView>, например класс <xref:System.Windows.Forms.BindingSource>.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает привязку данных к общедоступным свойствам объектов, возвращенным этими интерфейсами, или к коллекции свойств, возвращенной интерфейсом <xref:System.ComponentModel.ICustomTypeDescriptor>, если он был реализован в возвращенных объектах.  
  
 Обычно привязка осуществляется к компоненту <xref:System.Windows.Forms.BindingSource>, а компонент <xref:System.Windows.Forms.BindingSource> связывается с другим источником данных или заполняется бизнес\-объектами.  Компонент <xref:System.Windows.Forms.BindingSource> является предпочтительным, так как обеспечивает привязку к различным типам источников данных и может автоматически разрешать различные проблемы привязки данных.  Дополнительные сведения см. в разделе [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> также может применяться в *несвязанном* режиме, без базового хранилища данных.  Пример кода, в котором используется несвязанный элемент управления <xref:System.Windows.Forms.DataGridView>, содержится в разделе [Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> можно легко настроить и расширить. Кроме того, элемент управления предоставляет множество свойств, методов и событий, позволяющих настроить внешний вид и поведение.  Если требуется отображение табличных данных с помощью приложения Windows Forms, рассмотрите возможность использования элемента управления <xref:System.Windows.Forms.DataGridView>, прежде чем рассматривать другие решения \(например, <xref:System.Windows.Forms.DataGrid>\).  Если требуется отображение сетки с небольшим объемом данных только для чтения или предоставление пользователю возможности редактирования таблицы с миллионами записей, можно использовать элемент управления <xref:System.Windows.Forms.DataGridView>, отличающийся эффективным использованием памяти и быстрым программированием.  
  
## Содержание  
 [Технологическая сводка по элементам управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Общие сведения об элементе управления <xref:System.Windows.Forms.DataGridView> и использовании связанных с ним классов.  
  
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Описание архитектуры элемента управления <xref:System.Windows.Forms.DataGridView>, объяснение его иерархии типов и структуры наследования.  
  
 [Сценарии использования элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Описание стандартных сценариев, в которых используются элементы управления <xref:System.Windows.Forms.DataGridView>.  
  
 [Примеры кода для элемента управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Ссылки на документацию с примерами кода для выполнения различных задач <xref:System.Windows.Forms.DataGridView>.  Примеры распределены на категории по типам.  
  
## Связанные разделы  
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Обсуждение типов столбцов в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, использующемся для отображения данных и позволяющем пользователям изменять или добавлять данные.  
  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Список разделов, в которых описаны способы заполнения элемента управления данными вручную или с помощью внешнего источника данных.  
  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Список разделов, в которых описывается пользовательская окраска ячеек и строк <xref:System.Windows.Forms.DataGridView> и создание производных типов ячеек, строк и столбцов.  
  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Список разделов, в которых описываются эффективные способы использования элемента управления, позволяющие избежать снижения производительности при работе с большими объемами данных.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Стандартная функциональность элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)   
 [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)