---
title: Изменение размеров управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: a8e2e05877746dfb043b7e8ac2a6c2b7017883c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960423"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Изменение размеров управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView>Размер строк, столбцов и заголовков может изменяться в результате множества различных вхождений. Эти вхождения показаны в следующей таблице.  
  
|Однократно|Описание|  
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
|Используйте режим заполнения столбца с отображаемыми значениями различных размеров.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Инициализируйте относительную ширину столбцов путем задания <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> свойств столбца или путем вызова метода <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> элемента управления после заполнения элемента управления данными.|  
|Используйте режим заполнения столбца со значениями различной важности.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Задайте большие <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> значения для столбцов, которые всегда должны отображать некоторые данные, или используйте параметр изменения размера, отличный от режима заполнения для определенных столбцов.|  
|Используйте режим заполнения столбца, чтобы не отображать фон элемента управления.|Задайте для <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> свойства последнего столбца значение и используйте другие параметры изменения размера для других столбцов. Если другие столбцы используют слишком много доступного пространства, установите <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> свойство последнего столбца.|  
|Отображение столбца фиксированной ширины, например столбца со значком или ИДЕНТИФИКАТОРом.|Задайте <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>для значение <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> и для<xref:System.Windows.Forms.DataGridViewTriState.False> столбца. <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> Инициализируйте ее ширину, задав <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> свойство или вызвав метод элемента <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> управления после заполнения элемента управления данными.|  
|Автоматическое изменение размеров при изменении содержимого ячейки во избежание усечения и оптимизации использования пространства.|Задайте для свойства автоматическое изменение размера значение, представляющее режим изменения размеров на основе содержимого. Чтобы избежать снижения производительности при работе с большими объемами данных, используйте режим изменения размера, который вычисляет только отображаемые строки.|  
|Настройте размеры в соответствии со значениями в отображаемых строках, чтобы избежать снижения производительности при работе с большим количеством строк.|Используйте соответствующие значения перечисления режима изменения размера с автоматическим или программным изменением размера. Чтобы настроить размеры в соответствии со значениями в вновь отображаемых строках при прокрутке, вызовите метод изменения <xref:System.Windows.Forms.DataGridView.Scroll> размера в обработчике событий. Чтобы настроить пользователь дважды щелкнуть изменение размера, чтобы только значения в отображаемых строках определили новые размеры, вызовите метод изменения размера в <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> обработчике событий или <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> .|  
|Подгонять размеры в соответствии с содержимым ячеек только в определенное время, чтобы избежать снижения производительности или для включения изменения размера пользователя.|Вызов метода изменения размера на основе содержимого в обработчике событий. Например, используйте <xref:System.Windows.Forms.DataGridView.DataBindingComplete> событие для инициализации размеров после привязки и <xref:System.Windows.Forms.DataGridView.CellValidated> обработайте событие или <xref:System.Windows.Forms.DataGridView.CellValueChanged> для изменения размеров, чтобы компенсировать изменение пользователем или изменение в связанном источнике данных.|  
|Настройка высоты строк для многострочного содержимого ячеек.|Убедитесь, что ширина столбцов подходит для отображения абзацев текста, и используйте автоматическое или программное изменение размера строки на основе содержимого для настройки высоты. Также убедитесь, что ячейки с многострочным содержимым <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> отображаются с использованием <xref:System.Windows.Forms.DataGridViewTriState.True>значения стиля ячейки.<br /><br /> Обычно используется режим автоматического изменения размера столбца, чтобы сохранить ширину столбцов или задать для них определенные значения ширины до корректировки высоты строк.|  
  
## <a name="resizing-with-the-mouse"></a>Изменение размера с помощью мыши  
 По умолчанию пользователи могут изменять размер строк, столбцов и заголовков, которые не используют режим автоматического изменения размера на основе значений ячеек. Чтобы запретить пользователям изменять размеры в других режимах, например в режиме заполнения столбца, установите одно или несколько из следующих <xref:System.Windows.Forms.DataGridView> свойств:  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Можно также запретить пользователям изменять размеры отдельных строк или столбцов, задав их <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> свойства. По умолчанию <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> значение свойства основано <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> на <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> значении свойства для столбцов и значении свойства для строк. Если явно задано <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> <xref:System.Windows.Forms.DataGridViewTriState.True> значение или <xref:System.Windows.Forms.DataGridViewTriState.False>, то указанное значение переопределяет значения элемента управления для этой строки или столбца. Задайте <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> для<xref:System.Windows.Forms.DataGridViewTriState.NotSet> значение, чтобы восстановить наследование.  
  
 Поскольку <xref:System.Windows.Forms.DataGridViewTriState.NotSet> восстанавливает наследование значения <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> , <xref:System.Windows.Forms.DataGridViewTriState.NotSet> свойство никогда не будет возвращать значение, если строка <xref:System.Windows.Forms.DataGridView> или столбец не были добавлены в элемент управления. Если необходимо определить, наследуется <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> ли значение свойства строки или столбца, проверьте его <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство. Если значение включает флаг, <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> значение свойства не наследуется. <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> <xref:System.Windows.Forms.DataGridViewElement.State%2A>  
  
## <a name="automatic-sizing"></a>Автоматическое изменение размера  
 Существует два вида автоматического изменения размера в <xref:System.Windows.Forms.DataGridView> элементе управления: режим заполнения столбца и автоматическое изменение размеров на основе содержимого.  
  
 Режим заполнения столбца приводит к тому, что видимые столбцы в элементе управления заполняют ширину области отображения элемента управления. Дополнительные сведения об этом режиме см. [в разделе режим заполнения столбца в элементе управления Windows Forms DataGridView](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Кроме того, можно настроить автоматическое изменение размеров строк, столбцов и заголовков в соответствии с содержимым ячеек. В этом случае изменение размера происходит при каждом изменении содержимого ячейки.  
  
> [!NOTE]
> Если вы сохраняете значения ячеек в пользовательском кэше данных с помощью виртуального режима, автоматическое изменение размеров происходит, когда пользователь редактирует значение ячейки, но не происходит при изменении кэшированного значения вне <xref:System.Windows.Forms.DataGridView.CellValuePushed> обработчика событий. В этом случае вызовите <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> метод, чтобы заставить элемент управления обновить отображение ячейки и применить текущие режимы автоматического изменения размеров.  
  
 Если автоматическое изменение размера на основе содержимого включено только для одного измерения, то есть для строк, но не столбцов или для столбцов, но не строк — и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> также включено, корректировка размера также происходит при каждом изменении другого измерения. Например, если строки, но не столбцы настроены для автоматического изменения размера <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> и включены, пользователи могут перетаскивать разделители столбцов, чтобы изменить ширину столбцов, и высота строк будет автоматически скорректирована, чтобы содержимое ячеек по-прежнему отображалось полностью.  
  
 Если вы настроили как строки, так и столбцы для автоматического изменения <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> размеров на основе содержимого <xref:System.Windows.Forms.DataGridView> , то элемент управления будет изменять размеры при каждом изменении содержимого ячейки и будет использовать оптимальное соотношение высоты ячеек к ширине при вычислении новых размеров.  
  
 Чтобы настроить режим изменения размера для заголовков и строк, а также для столбцов, которые не переопределяют значение элемента управления, установите одно <xref:System.Windows.Forms.DataGridView> или несколько из следующих свойств:  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Чтобы переопределить режим изменения размера столбца элемента управления для отдельного столбца, установите для его <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> свойства значение, отличное от. <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet> Режим изменения размера для столбца фактически определяется его <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> свойством. Значение этого свойства основано на значении <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> свойства столбца, если это значение не равно <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, в этом случае <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение элемента управления наследуется.  
  
 Используйте автоматическое изменение размера на основе содержимого с осторожностью при работе с большими объемами данных. Чтобы избежать снижения производительности, используйте режимы автоматического изменения размеров, которые рассчитывают размеры на основе только отображаемых строк, а не анализируя каждую строку в элементе управления. Для максимальной производительности используйте программное изменение размера, чтобы можно было изменять размер в определенное время, например сразу после загрузки новых данных.  
  
 Режимы автоматического изменения размеров на основе содержимого не влияют на строки, столбцы или заголовки, которые были скрыты путем установки свойства строки или <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> столбца, а также <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> элементов <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> управления или `false`свойств в значение. Например, если столбец является скрытым после того, как он автоматически подбирается в соответствии с большим значением ячейки, то размер скрытого столбца не изменится, если строка, содержащая значение большой ячейки, будет удалена. Автоматическое изменение размера не происходит при изменении видимости, поэтому изменение свойства столбца <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> обратно на `true` не приведет к пересчету его размера на основе текущего содержимого.  
  
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
  
 Эти методы изменяют размер строк, столбцов или заголовков один раз, а не настраивают их для непрерывного изменения размера. Новые размеры рассчитываются автоматически для вывода всего содержимого ячейки без усечения. Однако при программном изменении размера столбцов, <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> имеющих <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>значения свойств, вычисляемые ширины на основе содержимого используются для пропорциональной корректировки значений свойств столбца <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> , а фактические ширины столбцов — Затем вычисляется в соответствии с новыми пропорциями, чтобы все столбцы заполнили доступную область экрана элемента управления.  
  
 Программное изменение размера полезно для предотвращения снижения производительности при постоянном изменении размера. Также полезно указать начальные размеры для строк, столбцов и заголовков, изменяемых пользователем, и для режима заполнения столбца.  
  
 Как правило, методы программного изменения размера вызываются в определенное время. Например, можно программно изменить размер всех столбцов сразу после загрузки данных или программно изменить размер определенной строки после того, как определенное значение ячейки было изменено.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Настройка поведения изменения размеров на основе содержимого  
 Можно настроить поведение при работе с производными <xref:System.Windows.Forms.DataGridView> типами ячеек, строк и столбцов, <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>переопределив методы, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>или <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> или вызвав защищенные перегрузки метода изменения размера в производном <xref:System.Windows.Forms.DataGridView> элемента. Защищенные перегрузки метода изменения размера предназначены для работы в виде пар, позволяющих достичь идеального соотношения высоты ячеек к ширине, избегая чрезмерно широких или высоких значений ячеек. Например, если `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` вызвать перегрузку <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> метода и `false` передать значение для <xref:System.Boolean> параметра, то перегрузка вычислит идеальные значения высоты и ширины ячеек в строке, но будет изменять высоту строк. только. Затем необходимо вызвать <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> метод, чтобы скорректировать ширину столбцов до вычисляемого идеального.  
  
## <a name="content-based-sizing-options"></a>Параметры размеров на основе содержимого  
 Перечисления, используемые свойствами и методами изменения размера, имеют аналогичные значения для определения размеров на основе содержимого. С помощью этих значений можно ограничить ячейки, используемые для вычисления предпочтительных размеров. Для всех перечислений размеров значения с именами, которые ссылаются на отображаемые ячейки, ограничивают свои вычисления ячейками в отображаемых строках. Исключение строк полезно во избежание снижения производительности при работе с большим количеством строк. Можно также ограничить вычисления значениями ячеек в заголовках или в ячейках, не отменяющих головное.  
  
## <a name="see-also"></a>См. также

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
- [Практическое руководство. Установка режима изменения размера элемента управления Windows Forms DataGridView](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
