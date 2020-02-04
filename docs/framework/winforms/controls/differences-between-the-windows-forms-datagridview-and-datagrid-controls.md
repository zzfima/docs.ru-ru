---
title: Различия между элементами управления DataGridView и DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745967"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Различия элементов управления DataGridView и DataGrid в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> — это новый элемент управления, который заменяет элемент управления <xref:System.Windows.Forms.DataGrid>. Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет множество основных и дополнительных функций, отсутствующих в элементе управления <xref:System.Windows.Forms.DataGrid>. Кроме того, архитектура элемента управления <xref:System.Windows.Forms.DataGridView> значительно упрощает его расширение и настройку, чем элемент управления <xref:System.Windows.Forms.DataGrid>.  
  
 В следующей таблице описаны некоторые основные функции, доступные в элементе управления <xref:System.Windows.Forms.DataGridView>, отсутствующие в элементе управления <xref:System.Windows.Forms.DataGrid>.  
  
|Функция элемента управления DataGridView|Description|  
|----------------------------------|-----------------|  
|Несколько типов столбцов|Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет больше встроенных типов столбцов, чем элемент управления <xref:System.Windows.Forms.DataGrid>. Эти типы столбцов отвечают потребностям наиболее распространенных сценариев, но их также легче расширять или заменять, чем типы столбцов в элементе управления <xref:System.Windows.Forms.DataGrid>. Дополнительные сведения см. [в разделе Типы столбцов в элементе управления Windows Forms DataGridView](column-types-in-the-windows-forms-datagridview-control.md).|  
|Несколько способов отобразить данные|Элемент управления <xref:System.Windows.Forms.DataGrid> ограничен отображением данных из внешнего источника данных. Однако элемент управления <xref:System.Windows.Forms.DataGridView> может отображать несвязанные данные, хранящиеся в элементе управления, данные из привязанного источника данных, а также связанные и непривязанные данные. Можно также реализовать виртуальный режим в элементе управления <xref:System.Windows.Forms.DataGridView>, чтобы обеспечить пользовательское управление данными. Дополнительные сведения см. [в разделе Режимы вывода данных в элементе управления Windows Forms DataGridView](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Различные способы настройки представления данных|Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет множество свойств и событий, которые позволяют указать способ форматирования и отображения данных. Например, можно изменить внешний вид ячеек, строк и столбцов в зависимости от содержащихся в них данных, а также заменить данные одного типа данными эквивалентными данными другого типа. Дополнительные сведения см. [в разделе Форматирование данных в элементе управления Windows Forms DataGridView](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Несколько параметров для изменения внешнего вида и поведения ячеек, строк, столбцов и заголовков|Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет работать с отдельными компонентами сетки множеством способов. Например, можно заморозить строки и столбцы, чтобы предотвратить их прокрутку. Скрытие строк, столбцов и заголовков; изменение способа корректировки размеров строк, столбцов и заголовков; изменение способа выбора пользователями. и предоставляют подсказки и контекстные меню для отдельных ячеек, строк и столбцов.|  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> сохраняется для обеспечения обратной совместимости и специальных потребностей. Для практически всех целей следует использовать элемент управления <xref:System.Windows.Forms.DataGridView>. Единственная функция, доступная в элементе управления <xref:System.Windows.Forms.DataGrid>, которая недоступна в элементе управления <xref:System.Windows.Forms.DataGridView>, является иерархическим отображением информации из двух связанных таблиц в одном элементе управления. Для отображения сведений из двух таблиц, которые находятся в связях "основной/подробности", необходимо использовать два элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Обновление элемента управления DataGridView  
 При наличии существующих приложений, использующих элемент управления <xref:System.Windows.Forms.DataGrid> в простом сценарии с привязкой к данным без настроек, можно просто заменить старый элемент управления новым. Оба элемента управления используют стандартную Windows Forms архитектуру привязки данных, поэтому элемент управления <xref:System.Windows.Forms.DataGridView> будет отображать привязанные данные без дополнительной настройки. Однако можно рассмотреть возможность использования улучшений привязки данных, но привяжите данные к <xref:System.Windows.Forms.BindingSource> компоненту, который затем можно привязать к элементу управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения см. в разделе [компонент BindingSource](bindingsource-component.md).  
  
 Поскольку элемент управления <xref:System.Windows.Forms.DataGridView> имеет совершенно новую архитектуру, нет прямого пути преобразования, который позволит использовать настройки <xref:System.Windows.Forms.DataGrid> с элементом управления <xref:System.Windows.Forms.DataGridView>. Однако многие настройки <xref:System.Windows.Forms.DataGrid> не являются обязательными для элемента управления <xref:System.Windows.Forms.DataGridView>, поскольку доступны встроенные функции нового элемента управления. Если вы создали пользовательские типы столбцов для элемента управления <xref:System.Windows.Forms.DataGrid>, который вы хотите использовать с элементом управления <xref:System.Windows.Forms.DataGridView>, потребуется реализовать их снова с помощью новой архитектуры. Дополнительные сведения см. [в разделе Настройка элемента управления Windows Forms DataGridView](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Компонент BindingSource](bindingsource-component.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Режимы отображения данных в элементе управления DataGridView в Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Форматирование данных в элементе управления DataGridView в Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Изменение размеров управления DataGridView в Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
