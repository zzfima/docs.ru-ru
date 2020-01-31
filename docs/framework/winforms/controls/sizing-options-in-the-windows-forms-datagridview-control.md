---
title: Параметры изменения размера в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: bf1be699a18608bb452bd9fb98cbca1e99f7a9e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742985"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Изменение размеров управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> строк, столбцов и заголовков может изменить размер в результате множества различных вхождений. Эти вхождения показаны в следующей таблице.  
  
|Повторение|Описание|  
|----------------|-----------------|  
|Изменение размера пользователя|Пользователи могут вносить корректировки размера, перетаскивая или дважды щелкая разделители строк, столбцов или заголовков.|  
|Изменение размера элемента управления|В режиме заполнения столбца ширина столбцов изменяется при изменении ширины элемента управления; Например, если элемент управления закреплен на родительской форме и пользователь изменяет размер формы.|  
|Изменение значения ячейки|В режимах автоматического изменения размеров на основе содержимого размеры меняются в соответствии с новыми отображаемыми значениями.|  
|Вызов метода|Программное изменение размера на основе содержимого позволяет выполнять корректировки на основе значений ячеек во время вызова метода.|  
|Значение свойства|Можно также задать определенные значения высоты и ширины.|  
  
 По умолчанию изменение размера пользователя включено, автоматическое изменение размера отключено, а значения ячеек, превышающие ширину столбцов, обрезаются.  
  
 В следующей таблице приведены сценарии, которые можно использовать для настройки поведения по умолчанию или использования определенных параметров изменения размера для достижения определенных эффектов.  
  
|Сценарий|Реализация|  
|--------------|--------------------|  
|Используйте режим заполнения столбца для отображения данных одинакового размера в относительно небольшом числе столбцов, которые занимают всю ширину элемента управления без отображения горизонтальной полосы прокрутки.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Используйте режим заполнения столбца с отображаемыми значениями различных размеров.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Инициализируйте относительную ширину столбцов, задавая <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> свойства столбца или вызвав метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> элемента управления после заполнения элемента управления данными.|  
|Используйте режим заполнения столбца со значениями различной важности.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Задайте большие <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> значения для столбцов, которые всегда должны отображать некоторые данные или использовать параметр изменения размера, отличный от режима заполнения для определенных столбцов.|  
|Используйте режим заполнения столбца, чтобы не отображать фон элемента управления.|Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> последнего столбца значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> и используйте другие параметры изменения размера для других столбцов. Если другие столбцы используют слишком много доступного пространства, установите свойство <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> последнего столбца.|  
|Отображение столбца фиксированной ширины, например столбца со значком или ИДЕНТИФИКАТОРом.|Задайте для параметра <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> и <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> <xref:System.Windows.Forms.DataGridViewTriState.False> для столбца. Инициализируйте ее ширину, задав свойство <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> или вызвав метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> элемента управления после заполнения элемента управления данными.|  
|Автоматическое изменение размеров при изменении содержимого ячейки во избежание усечения и оптимизации использования пространства.|Задайте для свойства автоматическое изменение размера значение, представляющее режим изменения размеров на основе содержимого. Чтобы избежать снижения производительности при работе с большими объемами данных, используйте режим изменения размера, который вычисляет только отображаемые строки.|  
|Настройте размеры в соответствии со значениями в отображаемых строках, чтобы избежать снижения производительности при работе с большим количеством строк.|Используйте соответствующие значения перечисления режима изменения размера с автоматическим или программным изменением размера. Чтобы настроить размеры в соответствии со значениями в вновь отображаемых строках при прокрутке, вызовите метод изменения размера в обработчике <xref:System.Windows.Forms.DataGridView.Scroll> событий. Чтобы настроить пользователь дважды щелкнуть изменение размера, чтобы только значения в отображаемых строках определили новые размеры, вызовите метод изменения размера в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> или <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick>.|  
|Подгонять размеры в соответствии с содержимым ячеек только в определенное время, чтобы избежать снижения производительности или для включения изменения размера пользователя.|Вызов метода изменения размера на основе содержимого в обработчике событий. Например, используйте событие <xref:System.Windows.Forms.DataGridView.DataBindingComplete> для инициализации размеров после привязки и обработайте событие <xref:System.Windows.Forms.DataGridView.CellValidated> или <xref:System.Windows.Forms.DataGridView.CellValueChanged>, чтобы изменить размеры, чтобы компенсировать изменение пользователем или изменение в связанном источнике данных.|  
|Настройка высоты строк для многострочного содержимого ячеек.|Убедитесь, что ширина столбцов подходит для отображения абзацев текста, и используйте автоматическое или программное изменение размера строки на основе содержимого для настройки высоты. Также убедитесь, что ячейки с многострочным содержимым отображаются с помощью <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> значения стиля ячейки <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> Обычно используется режим автоматического изменения размера столбца, чтобы сохранить ширину столбцов или задать для них определенные значения ширины до корректировки высоты строк.|  
  
## <a name="resizing-with-the-mouse"></a>Изменение размера с помощью мыши  
 По умолчанию пользователи могут изменять размер строк, столбцов и заголовков, которые не используют режим автоматического изменения размера на основе значений ячеек. Чтобы запретить пользователям изменять размеры в других режимах, например в режиме заполнения столбца, задайте одно или несколько следующих свойств <xref:System.Windows.Forms.DataGridView>.  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Можно также запретить пользователям изменять размеры отдельных строк или столбцов, задав их свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>. По умолчанию значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> основано на значении свойства <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> для столбцов и значения свойства <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> для строк. Однако если явно задать <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> для <xref:System.Windows.Forms.DataGridViewTriState.True> или <xref:System.Windows.Forms.DataGridViewTriState.False>, то указанное значение переопределяет значение элемента управления для этой строки или столбца. Задайте для параметра <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> значение <xref:System.Windows.Forms.DataGridViewTriState.NotSet>, чтобы восстановить наследование.  
  
 Поскольку <xref:System.Windows.Forms.DataGridViewTriState.NotSet> восстанавливает наследование значения, свойство <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> никогда не будет возвращать значение <xref:System.Windows.Forms.DataGridViewTriState.NotSet>, если строка или столбец не были добавлены в элемент управления <xref:System.Windows.Forms.DataGridView>. Если необходимо определить, наследуется ли значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> строки или столбца, изучите его свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A>. Если <xref:System.Windows.Forms.DataGridViewElement.State%2A> значение включает флаг <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>, значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> не наследуется.  
  
## <a name="automatic-sizing"></a>Автоматическое изменение размера  
 Существует два вида автоматического изменения размеров в элементе управления <xref:System.Windows.Forms.DataGridView>: режим заполнения столбца и автоматическое изменение размеров на основе содержимого.  
  
 Режим заполнения столбца приводит к тому, что видимые столбцы в элементе управления заполняют ширину области отображения элемента управления. Дополнительные сведения об этом режиме см. [в разделе режим заполнения столбца в элементе управления Windows Forms DataGridView](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Кроме того, можно настроить автоматическое изменение размеров строк, столбцов и заголовков в соответствии с содержимым ячеек. В этом случае изменение размера происходит при каждом изменении содержимого ячейки.  
  
> [!NOTE]
> Если вы сохраняете значения ячеек в пользовательском кэше данных с помощью виртуального режима, автоматическое изменение размеров происходит, когда пользователь редактирует значение ячейки, но не происходит при изменении кэшированного значения за пределами <xref:System.Windows.Forms.DataGridView.CellValuePushed> обработчика событий. В этом случае вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>, чтобы заставить элемент управления обновить отображение ячейки и применить текущие режимы автоматического изменения размеров.  
  
 Если автоматическое изменение размера на основе содержимого включено только для одного измерения, то есть для строк, но не столбцов или для столбцов, но не строк — и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> также включен, коррекция размера также происходит при каждом изменении другого измерения. Например, если строки, но не столбцы настроены для автоматического изменения размера, а <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> включен, пользователи могут перетаскивать разделители столбцов, чтобы изменить ширину столбцов, и высота строк будет автоматически скорректирована, чтобы содержимое ячеек по-прежнему отображалось полностью.  
  
 Если настроить как строки, так и столбцы для автоматического изменения размеров на основе содержимого, а <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> включен, то элемент управления <xref:System.Windows.Forms.DataGridView> будет изменять размеры при каждом изменении содержимого ячейки и будет использовать оптимальное соотношение высоты ячеек к ширине при вычислении новых размеров.  
  
 Чтобы настроить режим изменения размера для заголовков и строк, а также для столбцов, которые не переопределяют значение элемента управления, установите одно или несколько следующих свойств <xref:System.Windows.Forms.DataGridView>.  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Чтобы переопределить режим изменения размера столбца элемента управления для отдельного столбца, задайте для его свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> значение, отличное от <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. Режим изменения размера для столбца фактически определяется его свойством <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>. Значение этого свойства основано на значении свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> столбца, если это значение не равно <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, в этом случае наследуется значение <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> элемента управления.  
  
 Используйте автоматическое изменение размера на основе содержимого с осторожностью при работе с большими объемами данных. Чтобы избежать снижения производительности, используйте режимы автоматического изменения размеров, которые рассчитывают размеры на основе только отображаемых строк, а не анализируя каждую строку в элементе управления. Для максимальной производительности используйте программное изменение размера, чтобы можно было изменять размер в определенное время, например сразу после загрузки новых данных.  
  
 Режимы автоматического изменения размеров на основе содержимого не влияют на строки, столбцы или заголовки, которые были скрыты путем установки свойства <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> строк или столбцов, а также <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> или свойств элемента управления <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> `false`. Например, если столбец является скрытым после того, как он автоматически подбирается в соответствии с большим значением ячейки, то размер скрытого столбца не изменится, если строка, содержащая значение большой ячейки, будет удалена. Автоматическое изменение размера не происходит при изменении видимости, поэтому изменение значения столбца <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> обратно на `true` не приведет к повторному вычислению его размера на основе текущего содержимого.  
  
 Программное изменение размера на основе содержимого влияет на строки, столбцы и заголовки, независимо от их видимости.  
  
## <a name="programmatic-resizing"></a>Программное изменение размера  
 Если автоматическое изменение размера отключено, можно программно задать точную ширину или высоту строк, столбцов или заголовков с помощью следующих свойств:  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Можно также программно изменять размер строк, столбцов и заголовков в соответствии с их содержимым с помощью следующих методов:  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Эти методы изменяют размер строк, столбцов или заголовков один раз, а не настраивают их для непрерывного изменения размера. Новые размеры рассчитываются автоматически для вывода всего содержимого ячейки без усечения. Однако при программном изменении размера столбцов, имеющих <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> значений свойств <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, вычисляемые ширины на основе содержимого используются для пропорциональной корректировки значений свойств столбца <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>, а фактические значения ширины столбцов вычисляются в соответствии с новыми пропорциями, чтобы все столбцы заполнили доступную область экрана элемента управления.  
  
 Программное изменение размера полезно для предотвращения снижения производительности при постоянном изменении размера. Также полезно указать начальные размеры для строк, столбцов и заголовков, изменяемых пользователем, и для режима заполнения столбца.  
  
 Как правило, методы программного изменения размера вызываются в определенное время. Например, можно программно изменить размер всех столбцов сразу после загрузки данных или программно изменить размер определенной строки после того, как определенное значение ячейки было изменено.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Настройка поведения изменения размеров на основе содержимого  
 Можно настроить поведение при работе с производными <xref:System.Windows.Forms.DataGridView> типами ячеек, строк и столбцов путем переопределения методов <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>или <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> или путем вызова перегрузок метода с модификатором protected в производном элементе управления <xref:System.Windows.Forms.DataGridView>. Защищенные перегрузки метода изменения размера предназначены для работы в виде пар, позволяющих достичь идеального соотношения высоты ячеек к ширине, избегая чрезмерно широких или высоких значений ячеек. Например, если вызвать перегрузку `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` метода <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> и передать значение `false` для параметра <xref:System.Boolean>, то перегрузка вычислит идеальные значения высоты и ширины ячеек в строке, но будет корректировать только высоту строк. Затем необходимо вызвать метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>, чтобы изменить ширину столбца на вычисленный идеальный.  
  
## <a name="content-based-sizing-options"></a>Параметры размеров на основе содержимого  
 Перечисления, используемые свойствами и методами изменения размера, имеют аналогичные значения для определения размеров на основе содержимого. С помощью этих значений можно ограничить ячейки, используемые для вычисления предпочтительных размеров. Для всех перечислений размеров значения с именами, которые ссылаются на отображаемые ячейки, ограничивают свои вычисления ячейками в отображаемых строках. Исключение строк полезно во избежание снижения производительности при работе с большим количеством строк. Можно также ограничить вычисления значениями ячеек в заголовках или в ячейках, не отменяющих головное.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
