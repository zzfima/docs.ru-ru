---
title: Технологическая сводка по элементам управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 18eebd067df9768e14cc81258184551d00dd1402
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742481"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Технологическая сводка по элементам управления DataGridView (Windows Forms)
В этом разделе содержится сводная информация о системе управления `DataGridView` и классах, поддерживающих ее использование.  
  
 Отображение данных в табличном формате — это задача, которая, скорее всего, будет выполняться часто. Элемент управления `DataGridView` предназначен для полного решения для представления данных в сетке.  
  
## <a name="keywords"></a>Keywords  
 DataGridView, BindingSource, таблица, ячейка, привязка данных, виртуальный режим  
  
## <a name="namespaces"></a>Пространства имен  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Связанные технологии  
 `BindingSource`  
  
## <a name="background"></a>Историческая справка  
 Конструкторы ПОЛЬЗОВАТЕЛЬСКОГО интерфейса часто находят необходимость в отображении табличных данных пользователям. .NET Framework предоставляет несколько способов отображения данных в таблице или сетке. Элемент управления `DataGridView` представляет собой последнюю эволюцию этой технологии для Windows Forms приложений.  
  
 Элемент управления `DataGridView` может отображать строки данных из хранилища данных. Поддерживается множество типов хранилищ данных. Хранилище данных может содержать простые нетипизированные данные, такие как одномерный массив, или может содержать типизированные данные, например <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [инструкции. Привязка данных к элементу управления Windows Forms DataGridView](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Элемент управления `DataGridView` предоставляет мощный и гибкий способ отображения данных в табличном формате. Этот элемент управления можно использовать для отображения представлений, предназначенных только для чтения или для изменяемых небольших и очень больших наборов данных.  
  
 Можно расширить элемент управления `DataGridView` несколькими способами, чтобы создать пользовательское поведение в приложениях. Например, можно программно задать собственные алгоритмы сортировки, можно создать собственные типы ячеек. Внешний вид элемента управления `DataGridView` легко настраивается заданием значений нескольких свойств. В качестве источника данных можно использовать различные типы хранилищ данных, или элемент управления `DataGridView` может работать без привязанного к нему источника данных.  
  
## <a name="implementing-datagridview-classes"></a>Реализация классов DataGridView  
 Существует несколько способов воспользоваться преимуществами функций расширяемости элемента управления `DataGridView`. Вы можете настроить множество аспектов элемента управления с помощью событий и свойств, но некоторые настройки потребовали создания новых классов, производных от существующих `DataGridView` классов.  
  
 Наиболее часто используемыми базовыми классами являются `DataGridViewCell` и `DataGridViewColumn`. Можно создать собственный класс ячейки из `DataGridViewCell` или любого его дочернего класса. Хотя можно добавить любой тип ячеек в любой столбец, обычно он также является производным классом вспомогательного столбца от `DataGridViewColumn`, который по умолчанию содержит ячейки пользовательского типа ячейки.  
  
 Можно реализовать интерфейс `IDataGridViewEditingCell` в производном классе ячейки, чтобы создать тип ячейки, имеющий функциональность редактирования, но не размещающий элемент управления в режиме редактирования. Чтобы создать элемент управления, который можно разместить в ячейке в режиме правки, можно реализовать интерфейс `IDataGridViewEditingControl` в классе, производном от <xref:System.Windows.Forms.Control>.  
  
 Дополнительные сведения см. в разделе [как настроить ячейки и столбцы в элементе управления Windows Forms DataGridView путем расширения их поведения и внешнего вида](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) , а [также как размещать элементы управления в Windows Forms ячейках DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Краткий обзор классов DataGridView  
 <xref:System.Windows.Forms>  
  
|Область технологий|Классы, интерфейсы, элементы конфигурации|  
|---------------------|-------------------------------------------------|  
|Привязка данных|<xref:System.Windows.Forms.BindingSource>|  
|Представление данных|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|Расширяемость <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>What's New  
 Элемент управления <xref:System.Windows.Forms.DataGridView> разработан как полноценное решение для отображения табличных данных с помощью Windows Forms. Рекомендуется использовать элемент управления <xref:System.Windows.Forms.DataGridView> перед другими решениями, например <xref:System.Windows.Forms.DataGrid>, при создании нового приложения. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> может работать в тесном соединении с компонентом <xref:System.Windows.Forms.BindingSource>. Этот компонент предназначен для использования в качестве основного источника данных формы. Он может управлять взаимодействием между элементом управления <xref:System.Windows.Forms.DataGridView> и его источником данных независимо от типа источника данных.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления DataGridView](datagridview-control-overview-windows-forms.md)
- [Архитектура элементов управления DataGridView](datagridview-control-architecture-windows-forms.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
