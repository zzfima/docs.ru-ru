---
title: Технологическая сводка по элементам управления DataGridView (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: cafd832e7105540ae684dd1feb4b33ab74f72836
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528877"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Технологическая сводка по элементам управления DataGridView (Windows Forms)
В этом разделе содержится сводная информация о системе управления `DataGridView` и классах, поддерживающих ее использование.  
  
 Отображение данных в табличном формате — это задача, которая обычно часто выполняется. `DataGridView` Элемент управления предназначен для законченное решение для представления данных в виде таблицы.  
  
## <a name="keywords"></a>Ключевые слова  
 DataGridView, BindingSource, таблицу, ячейки, привязка данных, виртуальный режим  
  
## <a name="namespaces"></a>Пространства имен  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Связанные технологии  
 `BindingSource`  
  
## <a name="background"></a>Фон  
 Разработчики пользовательского интерфейса (UI) часто бывает нужно отображать табличных данных для пользователей. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет несколько способов отображения данных в виде таблицы или сетки. `DataGridView` Управления представляет собой новейшее развитие этой технологии для приложений Windows Forms.  
  
 `DataGridView` Элемент управления может отображать строки данных из хранилища данных. Поддерживаются различные типы хранилищ данных. Хранилище данных может содержать простые, нетипизированные данные, такие как одномерный массив, так и типизированные данные, такие как <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [как: привязка данных к элементу управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Элемент управления `DataGridView` предоставляет мощный и гибкий способ отображения данных в табличном формате. Элемент управления можно использовать для отображения представления только для чтения или для редактирования мало для очень больших наборов данных.  
  
 Вы можете расширить `DataGridView` управления несколькими способами, чтобы реализовать пользовательское поведение в приложениях. Например, можно программно задать собственные алгоритмы сортировки, можно создать собственные типы ячеек. Внешний вид элемента управления `DataGridView` легко настраивается заданием значений нескольких свойств. Различные типы хранилищ данных может использоваться как источник данных или `DataGridView` управления могут работать без источника данных, привязанным к нему.  
  
## <a name="implementing-datagridview-classes"></a>Реализация классов DataGridView  
 Существует несколько способов, позволяющих воспользоваться преимуществами `DataGridView` функций расширения элемента управления. Можно настраивать различные аспекты управления через свойства и события, но некоторые настройки требуется создание новых классов, производных от существующих `DataGridView` классы.  
  
 Наиболее часто используемые базовые классы являются `DataGridViewCell` и `DataGridViewColumn`. Можно наследовать свой собственный класс ячейки с `DataGridViewCell` или любого из его дочерних классов. Несмотря на то, что в любой столбец можно добавить любой тип ячеек, будут обычно также дополнительное столбца класс наследуется от `DataGridViewColumn` , на котором размещается ячейки пользовательского типа по умолчанию.  
  
 Можно реализовать `IDataGridViewEditingCell` интерфейса в классе производная ячейка для создания типа ячеек, поддерживающего возможности редактирования, но не содержит элемент управления в режиме редактирования. Чтобы создать элемент управления, который можно разместить в ячейке в режиме редактирования, можно реализовать `IDataGridViewEditingControl` производными интерфейса в классе <xref:System.Windows.Forms.Control>.  
  
 Дополнительные сведения см. в разделе [как: Настройка ячеек и столбцов в элементе управления DataGridView Windows Forms, расширяя их поведение и внешний вид](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) и [как: элементы управления ведущего приложения в ячеек элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Краткий обзор классов DataGridView  
 <xref:System.Windows.Forms>  
  
|Область технологий|Классы, интерфейсы, элементы конфигурации|  
|---------------------|-------------------------------------------------|  
|Привязка данных|<xref:System.Windows.Forms.BindingSource>|  
|Представление данных|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Расширяемость|<xref:System.Windows.Forms.DataGridViewCell> и производные классы<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> и производные классы<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Новые возможности  
 <xref:System.Windows.Forms.DataGridView> Элемент управления предназначен для законченное решение для представления табличных данных с помощью Windows Forms. Следует рассмотреть возможность использования <xref:System.Windows.Forms.DataGridView> элемента управления перед другим решениям, такого как <xref:System.Windows.Forms.DataGrid>, при разработке нового приложения. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 <xref:System.Windows.Forms.DataGridView> Управления могут работать в сочетании с <xref:System.Windows.Forms.BindingSource> компонента. Данный компонент разработан для первичного источника данных формы. Он управляет взаимодействием между <xref:System.Windows.Forms.DataGridView> управления и источником данных, независимо от того, данные типа источника.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md)
