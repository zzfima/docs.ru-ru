---
title: Рекомендации по масштабированию элемента управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744135"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Масштабирование элемента управления DataGridView в Windows Forms

Элемент управления <xref:System.Windows.Forms.DataGridView> предназначен для обеспечения максимальной масштабируемости. Если требуется отображать большие объемы данных, следуйте рекомендациям, описанным в этом разделе, чтобы избежать чрезмерного использования памяти или снижения скорости реагирования пользовательского интерфейса. В этом разделе обсуждаются следующие проблемы.

- Эффективное использование стилей ячеек

- Эффективное использование контекстных меню

- Эффективное использование автоматического изменения размера

- Эффективное использование коллекций выбранных ячеек, строк и столбцов

- Использование общих строк

- Предотвращение недоступности строк

При наличии особых потребностей в производительности можно реализовать виртуальный режим и предоставить собственные операции управления данными. Дополнительные сведения см. [в разделе Режимы вывода данных в элементе управления Windows Forms DataGridView](data-display-modes-in-the-windows-forms-datagridview-control.md).

## <a name="using-cell-styles-efficiently"></a>Эффективное использование стилей ячеек

Каждая ячейка, строка и столбец могут иметь свои собственные сведения о стиле. Сведения о стиле хранятся в <xref:System.Windows.Forms.DataGridViewCellStyle>ных объектах. Создание объектов стиля ячейки для многих отдельных элементов <xref:System.Windows.Forms.DataGridView> может оказаться неэффективным, особенно при работе с большими объемами данных. Чтобы избежать снижения производительности, используйте следующие рекомендации.

- Избегайте задания свойств стиля ячейки для отдельных <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewRow> объектов. Сюда входит объект Row, заданный свойством <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Каждая новая строка, клонированная из шаблона строки, получит собственную копию объекта стиля ячейки шаблона. Для обеспечения максимальной масштабируемости задайте свойства стиля ячейки на уровне <xref:System.Windows.Forms.DataGridView>. Например, задайте свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>, а не свойство <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>.

- Если для некоторых ячеек требуется форматирование, отличное от форматирования по умолчанию, используйте один и тот же экземпляр <xref:System.Windows.Forms.DataGridViewCellStyle> в группах ячеек, строк или столбцов. Избегайте прямого задания свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle> в отдельных ячейках, строках и столбцах. Пример общего доступа к стилю ячейки см. [в разделе как задать стили ячеек по умолчанию для элемента управления Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Можно также избежать снижения производительности при настройке стилей ячеек по отдельности, обрабатывая обработчик событий <xref:System.Windows.Forms.DataGridView.CellFormatting>. Пример см. в разделе [руководство. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).

- При определении стиля ячейки используйте свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>, а не свойство <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>. При доступе к свойству <xref:System.Windows.Forms.DataGridViewCell.Style%2A> создается новый экземпляр класса <xref:System.Windows.Forms.DataGridViewCellStyle>, если свойство еще не было использовано. Кроме того, этот объект может не содержать полные сведения о стиле для ячейки, если некоторые стили наследуются от строки, столбца или элемента управления. Дополнительные сведения о наследовании стилей ячеек см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="using-shortcut-menus-efficiently"></a>Эффективное использование контекстных меню

Каждая ячейка, строка и столбец могут иметь собственное контекстное меню. Контекстные меню в элементе управления <xref:System.Windows.Forms.DataGridView> представлены элементами управления <xref:System.Windows.Forms.ContextMenuStrip>. Как и объекты стиля ячейки, создание контекстных меню для многих отдельных элементов <xref:System.Windows.Forms.DataGridView> отрицательно сказывается на производительности. Чтобы избежать этого снижения, используйте следующие рекомендации.

- Избегайте создания контекстных меню для отдельных ячеек и строк. К ним относится шаблон строки, который клонируется вместе с контекстным меню при добавлении новых строк к элементу управления. Для обеспечения максимальной масштабируемости используйте только свойство <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> элемента управления, чтобы указать одно контекстное меню для всего элемента управления.

- Если требуется несколько контекстных меню для нескольких строк или ячеек, обработайте события <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> или <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>. Эти события позволяют самостоятельно управлять объектами контекстного меню, что позволяет настраивать производительность.

## <a name="using-automatic-resizing-efficiently"></a>Эффективное использование автоматического изменения размера

Размер строк, столбцов и заголовков может изменяться автоматически по мере изменения содержимого ячейки, чтобы все содержимое ячеек отображалось без усечения. Изменение режима изменения размеров может также изменить размер строк, столбцов и заголовков. Чтобы определить правильный размер, элемент управления <xref:System.Windows.Forms.DataGridView> должен проверить значение каждой ячейки, которую она должна разместить. При работе с большими наборами данных этот анализ может негативно сказаться на производительности элемента управления, когда происходит автоматическое изменение размера. Чтобы избежать снижения производительности, используйте следующие рекомендации.

- Старайтесь не использовать автоматическое изменение размера в элементе управления <xref:System.Windows.Forms.DataGridView> с большим набором строк. Если вы используете автоматическое изменение размера, измените размер только на основе отображаемых строк. Также используйте только отображаемые строки в виртуальном режиме.

  - Для строк и столбцов используйте поля `DisplayedCells` или `DisplayedCellsExceptHeaders` перечисления <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>и <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.

  - Для заголовков строк используйте поле <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> или <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> перечисления <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>.

- Для максимальной масштабируемости отключите автоматическое изменение размеров и используйте программное изменение размера.

Дополнительные сведения см. [в разделе Параметры изменения размера в элементе управления Windows Forms DataGridView](sizing-options-in-the-windows-forms-datagridview-control.md).

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Эффективное использование коллекций выбранных ячеек, строк и столбцов

<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>ная коллекция не работает эффективно с большим объемом выбора. Коллекции <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> также могут быть неэффективными, хотя в меньшую степень, так как количество строк в типичном элементе управления <xref:System.Windows.Forms.DataGridView> меньше, чем в ячейках, и число столбцов меньше, чем в строках. Чтобы избежать снижения производительности при работе с этими коллекциями, используйте следующие рекомендации.

- Чтобы определить, были ли выбраны все ячейки в <xref:System.Windows.Forms.DataGridView> перед доступом к содержимому коллекции <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, проверьте возвращаемое значение метода <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Однако обратите внимание, что этот метод может привести к тому, что строки не будут общими. Дополнительные сведения см. в следующем разделе.

- Избегайте использования свойства <xref:System.Collections.ICollection.Count%2A> <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType>, чтобы определить число выбранных ячеек. Вместо этого используйте метод <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> и передайте значение <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType>. Аналогичным образом, используйте методы <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType>, чтобы определить количество выбранных элементов вместо доступа к выбранным коллекциям строк и столбцов.

- Избегайте режимов выбора на основе ячеек. Вместо этого задайте для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

## <a name="using-shared-rows"></a>Использование общих строк

Эффективное использование памяти достигается в элементе управления <xref:System.Windows.Forms.DataGridView> с помощью общих строк. Строки будут совместно использовать как можно больше информации о их внешнем виде и поведении путем совместного использования экземпляров класса <xref:System.Windows.Forms.DataGridViewRow>.

При совместном использовании экземпляров строк экономится память, и строки могут быть недоступными для общего доступа. Например, каждый раз, когда пользователь взаимодействует с ячейкой напрямую, ее строка перестает быть общей. Так как это невозможно, рекомендации в этом разделе полезны только при работе с очень большими объемами данных и только тогда, когда пользователи взаимодействуют с относительно небольшой частью данных при каждом запуске программы.

Строка не может быть общей в непривязанном элементе управления <xref:System.Windows.Forms.DataGridView>, если какая-либо из ее ячеек содержит значения. Если элемент управления <xref:System.Windows.Forms.DataGridView> привязан к внешнему источнику данных или если вы реализуете виртуальный режим и предоставляете собственный источник данных, значения ячеек хранятся вне элемента управления, а не в объектах ячеек, что позволяет совместно использовать строки.

Объект строки может быть общим, только если состояние всех его ячеек может быть определено на основе состояния строки и состояний столбцов, содержащих ячейки. Если изменить состояние ячейки, чтобы она больше не была выведена из состояния ее строки и столбца, то она не может быть общей.

Например, строка не может использоваться совместно в следующих ситуациях:

- Строка содержит одну выбранную ячейку, которая не находится в выбранном столбце.

- Строка содержит ячейку с установленным свойством <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> или <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A>.

- Строка содержит <xref:System.Windows.Forms.DataGridViewComboBoxCell> с установленным свойством <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A>.

В режиме с привязкой или в виртуальном режиме можно предоставить подсказки и контекстные меню для отдельных ячеек, обрабатывая события <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> и <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>.

Элемент управления <xref:System.Windows.Forms.DataGridView> будет автоматически пытаться использовать общие строки при добавлении строк в <xref:System.Windows.Forms.DataGridViewRowCollection>. Чтобы обеспечить совместное использование строк, следуйте приведенным ниже рекомендациям.

- Избегайте вызова перегрузки `Add(Object[])` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> и `Insert(Object[])` перегрузки метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>. Эти перегрузки автоматически создают несовместное строки.

- Убедитесь, что строка, указанная в свойстве <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>, может использоваться совместно в следующих случаях:

  - При вызове `Add()` или `Add(Int32)` перегрузки метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> или `Insert(Int32,Int32)` перегрузки метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

  - При увеличении значения свойства <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType>.

  - При задании свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>.

- Убедитесь, что строка, указанная параметром `indexSource`, может использоваться совместно при вызове методов <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>и <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

- Убедитесь, что указанная строка или строки могут быть общими при вызове перегрузки `Add(DataGridViewRow)` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, метода <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>, `Insert(Int32,DataGridViewRow)` перегрузки метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> и метода <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

Чтобы определить, является ли строка общей, используйте метод <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> для получения объекта строки, а затем проверьте свойство <xref:System.Windows.Forms.DataGridViewBand.Index%2A> объекта. Общие строки всегда имеют свойство <xref:System.Windows.Forms.DataGridViewBand.Index%2A> со значением – 1.

## <a name="preventing-rows-from-becoming-unshared"></a>Предотвращение недоступности строк

Общие строки могут быть недоступными в результате выполнения кода или действия пользователя. Чтобы избежать снижения производительности, не следует выключать общий доступ к строкам. Во время разработки приложения можно выполнить обработку события <xref:System.Windows.Forms.DataGridView.RowUnshared>, чтобы определить, когда строки не будут общими. Это полезно при отладке проблем с общим доступом к строкам.

Чтобы предотвратить отменять общий доступ к строкам, следуйте приведенным ниже рекомендациям.

- Избегайте индексирования <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции или прохода по ней с помощью цикла `foreach`. Как правило, прямой доступ к строкам не требуется. <xref:System.Windows.Forms.DataGridView> методы, которые работают со строками, принимают аргументы индекса строк, а не экземпляры строк. Кроме того, обработчики для событий, связанных со строкой, получают объекты-аргументы событий со свойствами строк, которые можно использовать для работы с строками, не переставляя их в общий доступ.

- Если необходимо получить доступ к объекту строки, используйте метод <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> и передайте фактический индекс строки. Однако обратите внимание, что изменение объекта общей строки, полученного с помощью этого метода, приведет к изменению всех строк, совместно использующих этот объект. Однако строка для новых записей не используется совместно с другими строками, поэтому она не будет затронуты при изменении любой другой строки. Обратите внимание, что разные строки, представленные общей строкой, могут иметь разные контекстные меню. Чтобы получить правильное контекстное меню из общего экземпляра строки, используйте метод <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> и передайте фактический индекс строки. Если вместо этого вы получаете доступ к свойству <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> общей строки, он будет использовать общий индекс строки, равный-1, и не будет извлекать правильное контекстное меню.

- Избегайте индексирования коллекции <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType>. Прямой доступ к ячейке приведет к тому, что ее родительская строка станет недоступной, создавая новый <xref:System.Windows.Forms.DataGridViewRow>. Обработчики для событий, связанных с ячейками, получают объекты-аргументы событий со свойствами ячеек, которые можно использовать для работы с ячейками, не вызывая отменять общий доступ к строкам. Можно также использовать свойство <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> для получения индексов строк и столбцов текущей ячейки, не обращаясь к ячейке напрямую.

- Избегайте режимов выбора на основе ячеек. Эти режимы приводят к тому, что строки становятся недоступными. Вместо этого задайте для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

- Не обрабатывайте события <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType>. Эти события приводят к тому, что строки становятся недоступными. Кроме того, не вызывайте методы <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType>, которые вызывают эти события.

- Не следует обращаться к <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> коллекции, если свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. В результате все выбранные строки будут недоступными для общего доступа.

- Не вызывайте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType>. Этот метод может привести к тому, что строки не будут общими.

- Не вызывайте метод <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType>, если свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. Это приводит к тому, что все строки становятся недоступными.

- Не устанавливайте для свойства <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> или <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> ячейки значение `false`, если соответствующее свойство в столбце имеет значение `true`. Это приводит к тому, что все строки становятся недоступными.

- Не обращаться к свойству <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType>. Это приводит к тому, что все строки становятся недоступными.

- Не вызывайте перегрузку `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>. При сортировке с помощью пользовательского компаратора все строки становятся недоступными.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Виртуальный режим элемента управления DataGridView в Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Режимы отображения данных в элементе управления DataGridView в Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Изменение размеров управления DataGridView в Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
