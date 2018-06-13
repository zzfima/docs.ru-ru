---
title: Стили ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: 463fbbffe1e88991934f08fbe7e7445b2e233081
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529663"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Стили ячеек элемента управления DataGridView в Windows Forms
Каждая ячейка в <xref:System.Windows.Forms.DataGridView> элемент управления может иметь свой собственный стиль, включая формат текста, цвет фона, цвет и шрифт. Как правило, тем не менее, несколько ячеек обладают одинаковым стилем.  
  
 Группы ячеек с одинаковым стилем могут включать все ячейки в пределах определенного строк или столбцов, все ячейки с определенными значениями или все ячейки в элементе управления. Поскольку эти группы перекрываются, каждая ячейка может получать данные своего стиля из более чем в одном месте. Например, может потребоваться каждая ячейка <xref:System.Windows.Forms.DataGridView> использовать одинаковый шрифт, но только в столбцах для использования формат денежной единицы и только валюты ячейки с отрицательные числа красным основной цвет элемента управления.  
  
## <a name="the-datagridviewcellstyle-class"></a>Класс DataGridViewCellStyle  
 <xref:System.Windows.Forms.DataGridViewCellStyle> Класс содержит следующие свойства, относящиеся к стилю:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Этот класс также содержит следующие свойства, связанные с форматированием:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Дополнительные сведения об этих свойствах и другие свойства стиля ячейки см. в разделе <xref:System.Windows.Forms.DataGridViewCellStyle> справочной документации и в разделах, перечисленных в подразделе ниже.  
  
## <a name="using-datagridviewcellstyle-objects"></a>С помощью объектов DataGridViewCellStyle  
 Вы можете получить <xref:System.Windows.Forms.DataGridViewCellStyle> объекты из различных свойств <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, и <xref:System.Windows.Forms.DataGridViewCell> и их производные классы. Если одно из этих свойств еще не было задано, его значение было получено будет создана новая <xref:System.Windows.Forms.DataGridViewCellStyle> объекта. Можно также создать свои собственные <xref:System.Windows.Forms.DataGridViewCellStyle> объектов и назначьте их этих свойств.  
  
 Можно избежать ненужного дублирования информации о стилях, предоставив <xref:System.Windows.Forms.DataGridViewCellStyle> объектов между несколькими <xref:System.Windows.Forms.DataGridView> элементов. Поскольку стили элемента управления, столбца и фильтра строк уровней вниз до каждого уровня на уровне ячейки, можно также избежать дублирования стилей, задав только те свойства стилей на каждом уровне, которые отличаются от более высоких уровнях. Это описывается более подробно в следующем разделе наследования стиля.  
  
 В следующей таблице перечислены основные свойства, получить или задать <xref:System.Windows.Forms.DataGridViewCellStyle> объектов.  
  
|Свойство.|Классы|Описание|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>и производные классы|Возвращает или задает стили по умолчанию, используемые во все ячейки в весь элемент управления (включая заголовки), в столбце или в строке.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые во всех строках в элементе управления. Это относится к ячейкам заголовков.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые во чередующихся строк в элементе управления. Используется для создания эффекта бухгалтерской книги.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые в заголовках строк элемента управления. Текущую тему переопределены, если визуальные стили включены.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые в заголовках столбцов элемента управления. Текущую тему переопределены, если визуальные стили включены.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> и производные классы|Возвращает или задает стили, заданные на уровне ячеек. Эти стили заменяют унаследованные от более высоких уровнях.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>и производные классы|Получает все стили, примененные в ячейку, строку или столбец, включая стили, унаследованные от более высокого уровня.|  
  
 Как упоминалось выше, при получении значения свойства стиля автоматически создает новый <xref:System.Windows.Forms.DataGridViewCellStyle> объекта, если свойство не было задано ранее. Во избежание без необходимости создания этих объектов, строк и столбцов классы имеют <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> свойство, которое можно проверить, чтобы определить, является ли <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> свойства. Аналогично, классы ячейки имеют <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> свойство, которое указывает ли <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойства.  
  
 Каждое из свойств стиля имеет соответствующий *PropertyName* `Changed` события <xref:System.Windows.Forms.DataGridView> элемента управления. Для строк, столбцов и свойства ячейки, имя события начинается с «`Row`«,»`Column`», или «`Cell`» (например, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Каждое из этих событий возникает, когда соответствующее свойство стиля с другим <xref:System.Windows.Forms.DataGridViewCellStyle> объекта. Эти события не происходят при извлечении <xref:System.Windows.Forms.DataGridViewCellStyle> объекта из свойства стиля и изменении значений его свойств. Чтобы реагировать на изменения в самих объектов стиля ячейки, обрабатывать <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> событий.  
  
## <a name="style-inheritance"></a>Наследование стилей  
 Каждый <xref:System.Windows.Forms.DataGridViewCell> получает его внешний вид из его <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойство. <xref:System.Windows.Forms.DataGridViewCellStyle> Объект, возвращаемый этим свойством наследует значения от иерархии свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle>. Эти свойства перечислены ниже в порядке, в котором <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> для ячеек не заголовков получает свои значения.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (только для ячеек в строках нечетных)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для ячеек заголовков строк и столбцов <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойство заполняется значениями из следующего списка исходных свойств в определенном порядке.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Этот процесс показан на следующей схеме.  
  
 ![Свойства типа DataGridViewCellStyle](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 Также можно получить доступ к стилям, унаследованным от определенных строк и столбцов. Столбец <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> свойство наследует значения от следующих свойств.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Строка <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> свойство наследует значения от следующих свойств.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (только для ячеек в строках нечетных)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для каждого свойства в <xref:System.Windows.Forms.DataGridViewCellStyle> объект, возвращаемый `InheritedStyle` свойства, значение свойства извлекается из первого стиля ячейки в соответствующем списке, соответствующий свойству присвоено значение, отличное от <xref:System.Windows.Forms.DataGridViewCellStyle> класса значения по умолчанию.  
  
 В следующей таблице показано, как <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> наследуется от столбца, в котором значение свойства ячейка.  
  
|свойство типа `DataGridViewCellStyle`|Пример `ForeColor` значение для полученного объекта|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 В этом случае <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> значение из строки ячейки является первым действительным значением в списке. Это становится <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> значение свойства ячейки <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 На следующей схеме показана как разные <xref:System.Windows.Forms.DataGridViewCellStyle> свойства могут наследовать значения из разных мест.  
  
 ![Свойство DataGridView&#45;наследование значения](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 Используя преимущества наследования стиля, можно предоставить соответствующие стили для всего элемента управления без указания те же данные в нескольких местах.  
  
 Несмотря на то, что ячейки заголовка участвуют в наследовании стиля, как описано, объекты, возвращенные <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> свойства <xref:System.Windows.Forms.DataGridView> управления имеют начальные значения, переопределяющие значения свойств объекта, возвращенного <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойство. Если необходимо, чтобы свойства, установленные для объекта, возвращаемого <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойства, применяемый к заголовкам строк и столбцов, необходимо задать соответствующие свойства объектов, возвращенных <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> указанного значения по умолчанию для <xref:System.Windows.Forms.DataGridViewCellStyle> класса.  
  
> [!NOTE]
>  Если включены визуальные стили, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются текущей темы, заменяя все стили, указанные для этих свойств.  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, И <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> типы также инициализируют некоторые значения объекта, возвращаемого в столбце <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойство. Дополнительные сведения см. в справочной документации для этих типов.  
  
## <a name="setting-styles-dynamically"></a>Динамическая установка стилей  
 Чтобы настроить стили ячеек с определенными значениями, Реализуйте обработчик <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> событий. Обработчики для этого события получают аргумент <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> типа. Этот объект содержит свойства, позволяющие определить значение ячейки, подлежащего форматированию вместе с ее расположение в <xref:System.Windows.Forms.DataGridView> элемента управления. Этот объект также содержит <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> свойство, которое инициализируется значение <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойства форматируемой ячейки. Можно изменить свойства стиля ячейки и указать сведения о стиле, подходящие для значения ячейки и расположение.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.RowPrePaint> И <xref:System.Windows.Forms.DataGridView.RowPostPaint> событий также получать <xref:System.Windows.Forms.DataGridViewCellStyle> данных объектов событий, но в случае их это копия строки <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> свойство только для чтения в целях, и изменения не влияют на элементе управления.  
  
 Можно также динамически изменять стили отдельных ячеек в ответ на события, такие как <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.CellMouseLeave> события. Например, в обработчике <xref:System.Windows.Forms.DataGridView.CellMouseEnter> событий, можно сохранить текущее значение цвета фона ячеек (извлечь с помощью ячейки <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойства), установите его в новый цвет, который будет выделяться ячейки, при наведении указателя мыши. В обработчике <xref:System.Windows.Forms.DataGridView.CellMouseLeave> события, цвет фона можно будет восстановить исходное значение.  
  
> [!NOTE]
>  Кэширование значений, хранящихся в ячейке <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойства важно независимо от того, установлен ли значение определенного стиля. Если временно заменить параметр стиля, восстанавливая ее из копии в исходное состояние «не установлено» обеспечивает ячейки будет снова будет наследовать этот параметр стиля с более высокого уровня. Если вам нужно определить текущий стиль, действующий для ячейки независимо от того, наследуется ли стиль, использовать эту ячейку <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойство.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
