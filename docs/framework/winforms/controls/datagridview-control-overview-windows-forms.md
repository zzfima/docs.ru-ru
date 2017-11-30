---
title: "Общие сведения об элементе управления DataGridView (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4209866f63931fb3d80f35e211bd5f9b35ed48bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-overview-windows-forms"></a>Общие сведения об элементе управления DataGridView (Windows Forms)
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 С <xref:System.Windows.Forms.DataGridView> элемента управления, можно отображать и изменять табличные данные из различных типов источников данных.  
  
 Привязка данных к <xref:System.Windows.Forms.DataGridView> управление — это простой и интуитивно понятный и во многих случаях это просто параметр <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойство. При привязке к источнику данных, который содержит несколько списков или таблиц, задайте <xref:System.Windows.Forms.DataGridView.DataMember%2A> строковое значение, указывающее, списка или таблицы для привязки.  
  
 <xref:System.Windows.Forms.DataGridView> Элемент управления поддерживает стандартные Windows Forms модель привязки данных, поэтому он выполняет привязку к экземплярам классов, описанных в следующем списке:  
  
-   Любой класс, реализующий <xref:System.Collections.IList> интерфейс, включая одномерные массивы.  
  
-   Любой класс, реализующий <xref:System.ComponentModel.IListSource> интерфейса, такие как <xref:System.Data.DataTable> и <xref:System.Data.DataSet> классы.  
  
-   Любой класс, реализующий <xref:System.ComponentModel.IBindingList> интерфейса, такие как <xref:System.ComponentModel.BindingList%601> класса.  
  
-   Любой класс, реализующий <xref:System.ComponentModel.IBindingListView> интерфейса, такие как <xref:System.Windows.Forms.BindingSource> класса.  
  
 <xref:System.Windows.Forms.DataGridView> Управления поддерживает привязку данных к общим свойствам объектов, возвращенных эти интерфейсы или свойства коллекцию, возвращаемую <xref:System.ComponentModel.ICustomTypeDescriptor> интерфейс, если реализован в возвращаемых объектов.  
  
 Как правило, выполняется привязка к <xref:System.Windows.Forms.BindingSource> компонента и привязка <xref:System.Windows.Forms.BindingSource> компонент на другой источник данных или ее заполнение бизнес-объектов. <xref:System.Windows.Forms.BindingSource> Компонент является предпочтительным, так как его можно привязать к широкому спектру источников данных и может автоматически разрешать различные проблемы привязки данных. Дополнительные сведения см. в разделе [компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 <xref:System.Windows.Forms.DataGridView> Управления также может использоваться в *несвязанного* режиме без базового хранилища данных. Пример кода, использующего несвязанного <xref:System.Windows.Forms.DataGridView> управления см. в разделе [Пошаговое руководство: создание свободного элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 <xref:System.Windows.Forms.DataGridView> Управления высокой настраиваемыми и возможности расширения, а также многие свойства, методы и события для настройки внешнего вида и поведения. Если необходимо, чтобы приложение Windows Forms для отображения табличных данных, рассмотрите возможность использования <xref:System.Windows.Forms.DataGridView> управления перед другим пользователям (например, <xref:System.Windows.Forms.DataGrid>). При отображении небольшой сетки значений только для чтения, или если вы предоставляете пользователю возможность редактировать таблица с миллионами записей, <xref:System.Windows.Forms.DataGridView> управления предоставит вам легко программируемый памяти эффективное решение.  
  
## <a name="in-this-section"></a>Содержание  
 [Технологическая сводка по элементам управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Перечислены <xref:System.Windows.Forms.DataGridView> управления основные понятия и использование связанных классов.  
  
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Описывает архитектуру <xref:System.Windows.Forms.DataGridView> управления, объясняющий структура иерархии и наследования его типа.  
  
 [Сценарии использования элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Описание наиболее распространенных сценариев, в которых <xref:System.Windows.Forms.DataGridView> используются элементы управления.  
  
 [Примеры кода для элемента управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Содержит ссылки на примеры кода в документации для различных <xref:System.Windows.Forms.DataGridView> задачи. Примеры распределены на категории по типам задач.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Описание типов столбцов в Windows Forms <xref:System.Windows.Forms.DataGridView> управления используется для отображения сведений и разрешить пользователям изменять или добавлять данные.  
  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.  
  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.  
  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие, как эффективно использовать элемент управления, чтобы избежать снижения производительности при работе с большими объемами данных.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Стандартная функциональность элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
