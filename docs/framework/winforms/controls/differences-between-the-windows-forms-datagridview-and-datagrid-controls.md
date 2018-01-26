---
title: "Различия элементов управления DataGridView и DataGrid в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bc6d1fa2450d0aba52bd6a5a030c025fede0cb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Различия элементов управления DataGridView и DataGrid в Windows Forms
<xref:System.Windows.Forms.DataGridView> Управления имеет элемент управления, который заменяет <xref:System.Windows.Forms.DataGrid> элемента управления. <xref:System.Windows.Forms.DataGridView> Управления предоставляет множество основных и дополнительных компонентов, отсутствующих в <xref:System.Windows.Forms.DataGrid> элемента управления. Кроме того, архитектура <xref:System.Windows.Forms.DataGridView> управления позволяет легко можно расширять и настраивать чем <xref:System.Windows.Forms.DataGrid> элемента управления.  
  
 В следующей таблице описаны некоторые основные функции, доступные в <xref:System.Windows.Forms.DataGridView> управления, отсутствуют <xref:System.Windows.Forms.DataGrid> элемента управления.  
  
|Функция управления DataGridView|Описание:|  
|----------------------------------|-----------------|  
|Несколько типов столбцов|<xref:System.Windows.Forms.DataGridView> Управления предоставляет больше встроенных типов столбцов, чем <xref:System.Windows.Forms.DataGrid> элемента управления. Типы столбцов соответствуют наиболее распространенных сценариев, но могут оказаться легче расширять или заменять, чем типов столбцов в <xref:System.Windows.Forms.DataGrid> элемента управления. Дополнительные сведения см. в разделе [типов столбцов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Различные способы отображения данных|<xref:System.Windows.Forms.DataGrid> Управления может размещать данные из внешнего источника данных. <xref:System.Windows.Forms.DataGridView> Управления, тем не менее, могут отображать данные, хранящиеся в элемент управления, данные из связанного источника данных или данных, присоединенных и свободных друг с другом. Вы также можете реализовать виртуальный режим в <xref:System.Windows.Forms.DataGridView> управления для управления данными. Дополнительные сведения см. в разделе [режимы отображения данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Различные способы настройки отображения данных|<xref:System.Windows.Forms.DataGridView> Элемент управления предоставляет многие свойства и события, которые позволяют задать способ форматирования и отображения данных. Например можно изменить внешний вид ячеек, строк и столбцов в зависимости от данных, которые они содержат, или можно заменить данные одного типа данных другого типа. Дополнительные сведения см. в разделе [форматирование данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Несколько параметров для изменения ячейки, строки, столбца и заголовок внешний вид и поведение|<xref:System.Windows.Forms.DataGridView> Управления позволяет работать с отдельными компонентами таблицы различными способами. Например можно зафиксировать строки и столбцы, чтобы предотвратить прокрутку; скрытие строк, столбцов и заголовков; Изменение способа корректируются размеры строк, столбцов и заголовков; Изменение способа пользователей выбора; и укажите всплывающие подсказки и контекстные меню отдельных ячеек, строк и столбцов.|  
  
 <xref:System.Windows.Forms.DataGrid> Элемент управления можно сохранить для обратной совместимости и использования в определенных случаях. В целях почти все следует использовать <xref:System.Windows.Forms.DataGridView> элемента управления. Единственная функция, которая доступна в <xref:System.Windows.Forms.DataGrid> управления, который недоступен в <xref:System.Windows.Forms.DataGridView> управления — иерархическое отображение данных из двух связанных таблиц в одном элементе управления. Необходимо использовать два <xref:System.Windows.Forms.DataGridView> элементы управления для отображения данных из двух таблиц, которые находятся в иерархической связи.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Обновление для элемента управления DataGridView  
 При наличии существующих приложений, использующих <xref:System.Windows.Forms.DataGrid> элемента управления в простом сценарии с привязкой к данным без настройки, можно просто заменить старый элемент управления с помощью нового элемента управления. Оба элемента управления используют стандартную архитектуру привязки данных Windows Forms, поэтому <xref:System.Windows.Forms.DataGridView> элемент управления будет отображать связанные данные без дополнительной настройки. Может потребоваться рассмотреть использование преимуществ усовершенствования привязки данных, однако путем привязки данных к <xref:System.Windows.Forms.BindingSource> компонент, который затем можно привязать к <xref:System.Windows.Forms.DataGridView> элемента управления. Дополнительные сведения см. в разделе [компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Поскольку <xref:System.Windows.Forms.DataGridView> управления имеет новую архитектуру, отсутствует, можно использовать преобразование просто путь <xref:System.Windows.Forms.DataGrid> настроек с <xref:System.Windows.Forms.DataGridView> элемента управления. Многие <xref:System.Windows.Forms.DataGrid> настроек являются ненужными <xref:System.Windows.Forms.DataGridView> управления, однако из-за встроенной функции, доступные в новом элементе управления. Если вы создали пользовательские типы столбцов для <xref:System.Windows.Forms.DataGrid> управления, который вы хотите использовать с <xref:System.Windows.Forms.DataGridView> элемента управления, нужно будет реализовать снова с помощью новой архитектуры. Дополнительные сведения см. в разделе [Настройка элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
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
