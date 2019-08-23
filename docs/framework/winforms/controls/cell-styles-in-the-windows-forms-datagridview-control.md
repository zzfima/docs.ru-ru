---
title: Стили ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: be4c47db5c56685a84153a9ae4a9a2fe14c6adad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917757"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Стили ячеек элемента управления DataGridView в Windows Forms
Каждая ячейка в <xref:System.Windows.Forms.DataGridView> элементе управления может иметь собственный стиль, например текстовый формат, цвет фона, цвет переднего плана и шрифт. Однако обычно несколько ячеек будут иметь определенные характеристики стиля.  
  
 Группы ячеек с общими стилями могут включать в себя все ячейки в определенных строках или столбцах, все ячейки, содержащие определенные значения, или все ячейки в элементе управления. Поскольку эти группы перекрываются, каждая ячейка может получать сведения о стилях из нескольких мест. Например, может потребоваться, чтобы каждая ячейка в <xref:System.Windows.Forms.DataGridView> элементе управления использовала один и тот же шрифт, но только ячейки в столбцах валюты используют формат валюты и только ячейки валюты с отрицательными числами будут использовать красный цвет переднего плана.  
  
## <a name="the-datagridviewcellstyle-class"></a>Класс Датагридвиевцеллстиле  
 <xref:System.Windows.Forms.DataGridViewCellStyle> Класс содержит следующие свойства, связанные с визуальным стилем:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Этот класс также содержит следующие свойства, связанные с форматированием:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Дополнительные сведения об этих свойствах и других свойствах в стиле ячейки см. <xref:System.Windows.Forms.DataGridViewCellStyle> в справочной документации и в разделах, перечисленных в разделе "см. также" ниже.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Использование объектов Датагридвиевцеллстиле  
 Можно извлечь <xref:System.Windows.Forms.DataGridViewCellStyle> объекты из различных свойств <xref:System.Windows.Forms.DataGridView>классов, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>и <xref:System.Windows.Forms.DataGridViewCell> и их производных классов. Если одно из этих свойств еще не задано, при извлечении его значения будет создан новый <xref:System.Windows.Forms.DataGridViewCellStyle> объект. Можно также создать экземпляры собственных <xref:System.Windows.Forms.DataGridViewCellStyle> объектов и назначить их этим свойствам.  
  
 Чтобы избежать ненужного дублирования сведений о стиле <xref:System.Windows.Forms.DataGridViewCellStyle> , можно совместно <xref:System.Windows.Forms.DataGridView> использовать объекты из нескольких элементов. Поскольку стили, заданные на уровнях элементов управления, столбцов и строк, фильтруются по уровням ячеек, можно также избежать дублирования стилей, задав только свойства стиля на каждом уровне, отличающемся от уровней выше. Это описано более подробно в разделе Наследование стилей ниже.  
  
 В следующей таблице перечислены основные свойства, которые получают или устанавливают <xref:System.Windows.Forms.DataGridViewCellStyle> объекты.  
  
|Свойство.|Классы|Описание|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>,ипроизводныеклассы <xref:System.Windows.Forms.DataGridViewRow>|Возвращает или задает стили по умолчанию, используемые всеми ячейками во всем элементе управления (включая ячейки заголовка), в столбце или в строке.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые всеми строками в элементе управления. Сюда не входят ячейки заголовка.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые в чередующихся строках элемента управления. Используется для создания результата, аналогичного ГК.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые заголовками строк элемента управления. Переопределяется текущей темой, если включены стили оформления.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Возвращает или задает стили ячеек по умолчанию, используемые заголовками столбцов элемента управления. Переопределяется текущей темой, если включены стили оформления.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell>и производные классы|Возвращает или задает стили, заданные на уровне ячейки. Эти стили переопределяют те, которые унаследованы от более высоких уровней.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>,ипроизводныеклассы <xref:System.Windows.Forms.DataGridViewColumn>|Возвращает все стили, применяемые в данный момент к ячейке, строке или столбцу, включая стили, унаследованные от более высоких уровней.|  
  
 Как упоминалось выше, при получении значения свойства Style автоматически создается экземпляр нового <xref:System.Windows.Forms.DataGridViewCellStyle> объекта, если свойство не было задано ранее. Чтобы не создавать эти объекты без необходимости, классы строк и столбцов имеют <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> свойство, которое можно проверить, чтобы определить, было <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> ли установлено свойство. Аналогичным образом, классы ячеек имеют <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> свойство, указывающее, задано <xref:System.Windows.Forms.DataGridViewCell.Style%2A> ли свойство.  
  
 Каждое из свойств стиля имеет соответствующее событие *PropertyName* `Changed` в <xref:System.Windows.Forms.DataGridView> элементе управления. Для свойств строк, столбцов и ячеек имя`Row`события начинается с "", "`Column`" или "`Cell`" (например, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Каждое из этих событий возникает, когда соответствующему свойству Style присвоено <xref:System.Windows.Forms.DataGridViewCellStyle> значение другого объекта. Эти события не возникают при извлечении <xref:System.Windows.Forms.DataGridViewCellStyle> объекта из свойства Style и изменении его значений свойств. Чтобы реагировать на изменения самих объектов стиля ячейки, обрабатывайте <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> событие.  
  
## <a name="style-inheritance"></a>Наследование стилей  
 Каждый <xref:System.Windows.Forms.DataGridViewCell> из них получает свой внешний <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> вид из своего свойства. Объект, возвращаемый этим свойством, наследует свои значения из иерархии свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle>. <xref:System.Windows.Forms.DataGridViewCellStyle> Эти свойства перечислены ниже в том порядке, в котором ячейки <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> , не являющиеся заголовками, получают свои значения.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(только для ячеек в строках с нечетными номерами индекса)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для ячеек <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> заголовков строк и столбцов свойство заполняется значениями из следующего списка исходных свойств в заданном порядке.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Этот процесс показан на следующей схеме.  
  
 ![Свойства типа датагридвиевцеллстиле](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "Схема наследования датагридвиевцеллс")  
  
 Можно также получить доступ к стилям, наследуемым конкретными строками и столбцами. Свойство Column <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> наследует свои значения из следующих свойств.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Свойство Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> наследует свои значения из следующих свойств.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(только для ячеек в строках с нечетными номерами индекса)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Для каждого свойства <xref:System.Windows.Forms.DataGridViewCellStyle> объекта, возвращаемого `InheritedStyle` свойством, значение свойства получается из первого стиля ячейки в соответствующем списке, у которого соответствующее свойство имеет значение, отличное от <xref:System.Windows.Forms.DataGridViewCellStyle> значения по умолчанию для класса.  
  
 В следующей таблице показано, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> как значение свойства для ячейки примера наследуется из содержащего его столбца.  
  
|Свойство типа`DataGridViewCellStyle`|Пример `ForeColor` значения для полученного объекта|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 В этом случае <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> значение из строки ячейки является первым вещественным значением в списке. Это <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> свойство станет значением свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>ячейки.  
  
 На следующей схеме показано, как <xref:System.Windows.Forms.DataGridViewCellStyle> различные свойства могут наследовать свои значения из разных мест.  
  
 ![Наследование&#45;значения свойства DataGridView](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "Схема наследования значения датагридвиевцеллс")  
  
 Используя преимущества наследования стилей, можно предоставить соответствующие стили для всего элемента управления без необходимости указывать одни и те же сведения в нескольких местах.  
  
 Хотя ячейки заголовков участвуют в наследовании стиля, как описано, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> объекты <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> , возвращаемые <xref:System.Windows.Forms.DataGridView> свойствами и элемента управления, имеют начальные значения свойств, переопределяющие значения свойств объекта, возвращаемого <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойство. Если требуется, чтобы свойства объекта, <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> возвращаемого свойством, применялись к заголовкам строк и столбцов, необходимо задать соответствующие свойства объектов, возвращаемых <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> свойствами и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> , в значения по умолчанию, указанные <xref:System.Windows.Forms.DataGridViewCellStyle> для класса.  
  
> [!NOTE]
> Если включены стили оформления, заголовки строк и столбцов (кроме <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются по текущей теме, переопределяя все стили, заданные этими свойствами.  
  
 Типы, и <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridViewImageColumn> такжеинициализируютнекоторыезначенияобъекта,возвращаемогосвойствомColumn.<xref:System.Windows.Forms.DataGridViewCheckBoxColumn> <xref:System.Windows.Forms.DataGridViewButtonColumn> Дополнительные сведения см. в справочной документации по этим типам.  
  
## <a name="setting-styles-dynamically"></a>Динамическое задание стилей  
 Чтобы настроить стили ячеек с определенными значениями, реализуйте обработчик для <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> события. Обработчики для этого события получают аргумент <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> типа. Этот объект содержит свойства, позволяющие определить значение форматируемой ячейки и ее расположение в <xref:System.Windows.Forms.DataGridView> элементе управления. Этот объект также содержит <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> свойство, которое инициализируется значением <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойства форматируемой ячейки. Можно изменить свойства стиля ячейки, чтобы указать сведения о стиле, соответствующие значению ячейки и расположению.  
  
> [!NOTE]
> События <xref:System.Windows.Forms.DataGridView.RowPrePaint> <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> также получают <xref:System.Windows.Forms.DataGridViewCellStyle> объект в данных события, но в своем случае это копия свойства строки для целей только для чтения, а изменения в нем не влияют на элемент управления.  
  
 Можно также динамически изменять стили отдельных ячеек в ответ на такие события, как <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> события и. <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Например, в обработчике <xref:System.Windows.Forms.DataGridView.CellMouseEnter> события можно сохранить текущее значение цвета фона ячейки (полученное с помощью <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойства ячейки), а затем задать новый цвет, который будет выделять ячейку при наведении на нее указателя мыши. В обработчике для <xref:System.Windows.Forms.DataGridView.CellMouseLeave> события можно восстановить цвет фона до исходного значения.  
  
> [!NOTE]
> Кэширование значений, хранящихся в <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойстве ячейки, важно, независимо от того, задано ли конкретное значение стиля. Если вы временно заменили настройку стиля, ее восстановление в исходное состояние "не задано" гарантирует, что ячейка будет наследовать параметр стиля от более высокого уровня. Если необходимо определить фактический стиль, действующий для ячейки, независимо от того, унаследован ли этот стиль, используйте <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> свойство ячейки.  
  
## <a name="see-also"></a>См. также

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
- [Практическое руководство. Задать стили ячеек по умолчанию для элемента управления Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Форматирование данных в элементе управления DataGridView в Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
