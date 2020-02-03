---
title: Общие сведения об элементе управления DataGridView
ms.date: 03/30/2017
f1_keywords:
- DataGridView
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
ms.openlocfilehash: 74de5b449525be9ff93fcbef0ddabd041470177c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742496"
---
# <a name="datagridview-control-overview-windows-forms"></a>Общие сведения об элементе управления DataGridView (Windows Forms)
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно отображать и редактировать табличные данные из различных типов источников данных.  
  
 Привязка данных к элементу управления <xref:System.Windows.Forms.DataGridView> проста и интуитивно понятна, и во многих случаях это так же просто, как установка свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A>. При привязке к источнику данных, содержащему несколько списков или таблиц, задайте для свойства <xref:System.Windows.Forms.DataGridView.DataMember%2A> строку, указывающую список или таблицу для привязки.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную Windows Forms модель привязки данных, поэтому она будет привязана к экземплярам классов, описанным в следующем списке:  
  
- Любой класс, реализующий интерфейс <xref:System.Collections.IList>, включая одномерные массивы.  
  
- Любой класс, реализующий интерфейс <xref:System.ComponentModel.IListSource>, например классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet>.  
  
- Любой класс, реализующий интерфейс <xref:System.ComponentModel.IBindingList>, например класс <xref:System.ComponentModel.BindingList%601>.  
  
- Любой класс, реализующий интерфейс <xref:System.ComponentModel.IBindingListView>, например класс <xref:System.Windows.Forms.BindingSource>.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает привязку данных к открытым свойствам объектов, возвращаемых этими интерфейсами, или к коллекции свойств, возвращаемой интерфейсом <xref:System.ComponentModel.ICustomTypeDescriptor>, если они реализованы в возвращаемых объектах.  
  
 Как правило, привязка выполняется к компоненту <xref:System.Windows.Forms.BindingSource> и привязывает <xref:System.Windows.Forms.BindingSource> компонент к другому источнику данных или заполняет его бизнес-объектами. Компонент <xref:System.Windows.Forms.BindingSource> является предпочтительным источником данных, так как он может быть привязан к широкому спектру источников данных и может автоматически устранять множество проблем привязки данных. Дополнительные сведения см. в разделе [компонент BindingSource](bindingsource-component.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> можно также использовать в *несвязанном* режиме без базового хранилища данных. Пример кода, в котором используется несвязанный <xref:System.Windows.Forms.DataGridView> элемент управления, см. в разделе [Пошаговое руководство. Создание непривязанного элемента управления DataGridView Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> обладает широкими возможностями настройки и расширяем, и предоставляет множество свойств, методов и событий для настройки внешнего вида и поведения. Если вы хотите, чтобы в приложении Windows Forms отображались табличные данные, рассмотрите возможность использования элемента управления <xref:System.Windows.Forms.DataGridView> перед другими (например, <xref:System.Windows.Forms.DataGrid>). Если вы отображаете маленькую сетку значений, доступных только для чтения, или если вы предоставляете пользователю возможность редактировать таблицу с миллионами записей, то элемент управления <xref:System.Windows.Forms.DataGridView> предоставит вам легко Программируемое, эффективное решение для памяти.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Технологическая сводка по элементам управления DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Суммирует основные понятия управления <xref:System.Windows.Forms.DataGridView> и использование связанных классов.  
  
 [Архитектура элементов управления DataGridView](datagridview-control-architecture-windows-forms.md)  
 Описывает архитектуру элемента управления <xref:System.Windows.Forms.DataGridView>, объясняя его иерархию типов и структуру наследования.  
  
 [Сценарии использования элементов управления DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Описывает наиболее распространенные сценарии, в которых используются <xref:System.Windows.Forms.DataGridView> элементы управления.  
  
 [Примеры кода для элемента управления DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Содержит ссылки на примеры кода в документации по различным задачам <xref:System.Windows.Forms.DataGridView>. Примеры распределены на категории по типам задач.  
  
## <a name="related-sections"></a>См. также  
 [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Описание типов столбцов в Windows Forms элементе управления <xref:System.Windows.Forms.DataGridView>, используемых для вывода сведений и предоставления пользователям возможности изменять или добавлять данные.  
  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.  
  
 [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.  
  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие, как эффективно использовать элемент управления, чтобы избежать снижения производительности при работе с большими объемами данных.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Стандартная функциональность элемента управления DataGridView в Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
