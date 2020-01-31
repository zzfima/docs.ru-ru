---
title: Стили ячеек в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: fe56033a5adbe7719c64695c8f9ebc4f3644fc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746154"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Стили ячеек элемента управления DataGridView в Windows Forms
Каждая ячейка в элементе управления <xref:System.Windows.Forms.DataGridView> может иметь собственный стиль, например текстовый формат, цвет фона, цвет переднего плана и шрифт. Однако обычно несколько ячеек будут иметь определенные характеристики стиля.  
  
 Группы ячеек с общими стилями могут включать в себя все ячейки в определенных строках или столбцах, все ячейки, содержащие определенные значения, или все ячейки в элементе управления. Поскольку эти группы перекрываются, каждая ячейка может получать сведения о стилях из нескольких мест. Например, может потребоваться, чтобы каждая ячейка в элементе управления <xref:System.Windows.Forms.DataGridView> использовала один и тот же шрифт, но только ячейки в столбцах валюты используют формат валюты и только ячейки валюты с отрицательными числами будут использовать красный цвет переднего плана.  
  
## <a name="the-datagridviewcellstyle-class"></a>Класс Датагридвиевцеллстиле  
 Класс <xref:System.Windows.Forms.DataGridViewCellStyle> содержит следующие свойства, связанные с визуальным стилем.  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>.  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>.  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Этот класс также содержит следующие свойства, связанные с форматированием:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>.  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>.  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Дополнительные сведения об этих свойствах и других свойствах в стиле ячейки см. в справочной документации по <xref:System.Windows.Forms.DataGridViewCellStyle> и в разделах, перечисленных в разделе см. также ниже.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Использование объектов Датагридвиевцеллстиле  
 <xref:System.Windows.Forms.DataGridViewCellStyle> объекты можно получить из различных свойств классов <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>и <xref:System.Windows.Forms.DataGridViewCell> и их производных классов. Если одно из этих свойств еще не задано, при получении его значения будет создан новый объект <xref:System.Windows.Forms.DataGridViewCellStyle>. Можно также создать экземпляры собственных объектов <xref:System.Windows.Forms.DataGridViewCellStyle> и назначить их этим свойствам.  
  
 Можно избежать ненужного дублирования сведений о стиле, совместно используя объекты <xref:System.Windows.Forms.DataGridViewCellStyle> между несколькими <xref:System.Windows.Forms.DataGridView>ными элементами. Поскольку стили, заданные на уровнях элементов управления, столбцов и строк, фильтруются по уровням ячеек, можно также избежать дублирования стилей, задав только свойства стиля на каждом уровне, отличающемся от уровней выше. Это описано более подробно в разделе Наследование стилей ниже.  
  
 В следующей таблице перечислены основные свойства, которые получают или устанавливают <xref:System.Windows.Forms.DataGridViewCellStyle> объектов.  
  
|Идентификаторы|Классы|Описание|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>и производные классы|Возвращает или задает стили по умолчанию, используемые всеми ячейками во всем элементе управления (включая ячейки заголовка), в столбце или в строке.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые всеми строками в элементе управления. Сюда не входят ячейки заголовка.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые в чередующихся строках элемента управления. Используется для создания результата, аналогичного ГК.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые заголовками строк элемента управления. Переопределяется текущей темой, если включены стили оформления.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые заголовками столбцов элемента управления. Переопределяется текущей темой, если включены стили оформления.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> и производные классы|Возвращает или задает стили, заданные на уровне ячейки. Эти стили переопределяют те, которые унаследованы от более высоких уровней.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>и производные классы|Возвращает все стили, применяемые в данный момент к ячейке, строке или столбцу, включая стили, унаследованные от более высоких уровней.|  
  
 Как упоминалось выше, при получении значения свойства Style автоматически создается экземпляр нового объекта <xref:System.Windows.Forms.DataGridViewCellStyle>, если свойство не было задано ранее. Чтобы не создавать эти объекты без необходимости, классы строк и столбцов имеют свойство <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A>, которое можно проверить, чтобы определить, было ли установлено свойство <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>. Аналогичным образом, классы ячеек имеют свойство <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A>, которое указывает, задано ли свойство <xref:System.Windows.Forms.DataGridViewCell.Style%2A>.  
  
 Каждое из свойств стиля имеет соответствующее событие *PropertyName*`Changed` в элементе управления <xref:System.Windows.Forms.DataGridView>. Для свойств строк, столбцов и ячеек имя события начинается с "`Row`", "`Column`" или "`Cell`" (например, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Каждое из этих событий происходит, когда соответствующему свойству Style задается другой объект <xref:System.Windows.Forms.DataGridViewCellStyle>. Эти события не возникают при извлечении объекта <xref:System.Windows.Forms.DataGridViewCellStyle> из свойства Style и изменении его значений свойств. Чтобы реагировать на изменения самих объектов стиля ячейки, Обрабатывайте событие <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>.  
  
## <a name="style-inheritance"></a>Наследование стилей  
 Каждый <xref:System.Windows.Forms.DataGridViewCell> получает свой внешний вид из свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>. Объект <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемый этим свойством, наследует свои значения из иерархии свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle>. Эти свойства перечислены ниже в том порядке, в котором <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> для ячеек, не являющихся заголовками, получают свои значения.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (только для ячеек в строках с нечетными номерами индекса)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для ячеек заголовков строк и столбцов свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> заполняется значениями из следующего списка исходных свойств в заданном порядке.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Этот процесс показан на следующей схеме.  
  
 ![Свойства типа Датагридвиевцеллстиле](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "Схема наследования Датагридвиевцеллс")  
  
 Можно также получить доступ к стилям, наследуемым конкретными строками и столбцами. Свойство Column <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> наследует свои значения из следующих свойств.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Свойство Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> наследует свои значения из следующих свойств.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (только для ячеек в строках с нечетными номерами индекса)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для каждого свойства в объекте <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемом свойством `InheritedStyle`, значение свойства берется из первого стиля ячейки в соответствующем списке, для которого в соответствующем свойстве задано значение, отличное от значения по умолчанию для класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 В следующей таблице показано, как значение свойства <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> для ячейки примера наследуется из содержащего его столбца.  
  
|Свойство типа `DataGridViewCellStyle`|Пример `ForeColor` значения для полученного объекта|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 В этом случае <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> значение из строки ячейки является первым вещественным значением в списке. Это свойство принимает значение <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>ячейки.  
  
 На следующей схеме показано, как различные свойства <xref:System.Windows.Forms.DataGridViewCellStyle> могут наследовать свои значения из разных мест.  
  
 ![Наследование&#45;значения свойства DataGridView](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "Схема наследования значения Датагридвиевцеллс")  
  
 Используя преимущества наследования стилей, можно предоставить соответствующие стили для всего элемента управления без необходимости указывать одни и те же сведения в нескольких местах.  
  
 Хотя ячейки заголовка участвуют в наследовании стиля, как описано, объекты, возвращаемые свойствами <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView>, имеют начальные значения свойств, переопределяющие значения свойств объекта, возвращаемого свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Если требуется, чтобы свойства, возвращаемые свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, применялись к заголовкам строк и столбцов, необходимо задать соответствующие свойства объектов, возвращаемых <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> свойствам значений по умолчанию, указанных для класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
> [!NOTE]
> Если включены стили оформления, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются по текущей теме, переопределяя все стили, заданные этими свойствами.  
  
 Типы <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>и <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> также инициализируют некоторые значения объекта, возвращаемого свойством <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> столбца. Дополнительные сведения см. в справочной документации по этим типам.  
  
## <a name="setting-styles-dynamically"></a>Динамическое задание стилей  
 Чтобы настроить стили ячеек с определенными значениями, реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. Обработчики для этого события получают аргумент типа <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>. Этот объект содержит свойства, позволяющие определить значение отформатированной ячейки вместе с ее расположением в элементе управления <xref:System.Windows.Forms.DataGridView>. Этот объект также содержит свойство <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A>, которое инициализируется значением свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> отформатированной ячейки. Можно изменить свойства стиля ячейки, чтобы указать сведения о стиле, соответствующие значению ячейки и расположению.  
  
> [!NOTE]
> События <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> также получают объект <xref:System.Windows.Forms.DataGridViewCellStyle> в данных события, но в своем случае это копия свойства Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> для целей только для чтения, а изменения в нем не влияют на элемент управления.  
  
 Можно также динамически изменять стили отдельных ячеек в ответ на такие события, как события <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.CellMouseLeave>. Например, в обработчике события <xref:System.Windows.Forms.DataGridView.CellMouseEnter> можно сохранить текущее значение цвета фона ячейки (полученное с помощью свойства <xref:System.Windows.Forms.DataGridViewCell.Style%2A> ячейки), а затем задать новый цвет, который будет выделять ячейку при наведении на нее указателя мыши. В обработчике события <xref:System.Windows.Forms.DataGridView.CellMouseLeave> можно восстановить цвет фона в исходное значение.  
  
> [!NOTE]
> Кэширование значений, хранящихся в свойстве <xref:System.Windows.Forms.DataGridViewCell.Style%2A> ячейки, имеет значение, независимо от того, задано ли конкретное значение стиля. Если вы временно заменили настройку стиля, ее восстановление в исходное состояние "не задано" гарантирует, что ячейка будет наследовать параметр стиля от более высокого уровня. Если необходимо определить фактический стиль, действующий для ячейки, независимо от того, унаследован ли этот стиль, используйте свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> ячейки.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Форматирование данных в элементе управления DataGridView в Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
