---
title: Масштабирование элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 91153df539871de571375d7bf6d49d712a0c43b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Масштабирование элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Управления предназначен для обеспечения максимальной масштабируемости. Если требуется для отображения больших объемов данных, необходимо следовать инструкциям, описанным в этом разделе, чтобы избежать использования больших объемов памяти и снижения скорости реагирования пользовательского интерфейса (UI). В этом разделе обсуждаются следующие вопросы:  
  
-   Эффективное использование стили ячеек  
  
-   Эффективное использование контекстных меню  
  
-   Использование автоматического изменения размеров эффективно  
  
-   Эффективное использование выбранными коллекциями ячеек, строк и столбцов  
  
-   Использование общих строк  
  
-   Предотвращение строкам  
  
 Если у вас есть особые требования к производительности, можно реализовать виртуальный режим и предоставьте собственные операции управления данными. Дополнительные сведения см. в разделе [режимы отображения данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Эффективное использование стили ячеек  
 Каждый ячеек, строк и столбцов могут иметь свои собственные сведения о стиле. Сведения о стиле хранятся в <xref:System.Windows.Forms.DataGridViewCellStyle> объектов. Создание объектов стиля ячеек для большого числа <xref:System.Windows.Forms.DataGridView> элементы могут быть неэффективным, особенно при работе с большими объемами данных. Чтобы избежать снижения производительности, следуйте приведенным ниже рекомендациям:  
  
-   Не задавайте свойства стиля ячейки для отдельных <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewRow> объектов. Сюда входят строки объекта, заданного параметром <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство. Каждая новая строка, является клоном шаблона строки получит свою собственную копию шаблона объекта стиля ячейки. Для максимальной масштабируемости, задайте свойства стиля ячейки на <xref:System.Windows.Forms.DataGridView> уровне. Например, задать <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> свойства, а не <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> свойство.  
  
-   Если некоторые ячейки требуется форматирования, отличные от форматирования по умолчанию, используйте тот же идентификатор <xref:System.Windows.Forms.DataGridViewCellStyle> экземпляр групп ячеек, строк или столбцов. Избегайте прямого задания свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle> на отдельных ячеек, строк и столбцов. Пример совместного использования стиля ячеек см. в разделе [как: набор стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Можно также избежать снижения производительности при задании стили ячеек по отдельности, обрабатывая <xref:System.Windows.Forms.DataGridView.CellFormatting> обработчика событий. Пример см. в разделе [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   При определении стиля ячейки, используйте <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> свойства, а не <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> свойство. Доступ к <xref:System.Windows.Forms.DataGridViewCell.Style%2A> свойство создает новый экземпляр <xref:System.Windows.Forms.DataGridViewCellStyle> класса, если свойство еще не использовался. Кроме того этот объект может не содержать полные сведения о стиле для ячейки, если некоторые стили наследуются от строк, столбцов или элемента управления. Дополнительные сведения о наследовании стилей ячеек см. в разделе [стили ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Эффективное использование контекстных меню  
 Каждой ячейки, строки и столбца может иметь собственное контекстное меню. Контекстные меню в <xref:System.Windows.Forms.DataGridView> управления представляются <xref:System.Windows.Forms.ContextMenuStrip> элементов управления. Как и в случае с объектами стиля ячеек, создание контекстных меню для множества отдельных <xref:System.Windows.Forms.DataGridView> элементов может отрицательно сказаться на производительности. Чтобы избежать потерь производительности, следуйте приведенным ниже рекомендациям:  
  
-   Избегайте создания контекстных меню для отдельных ячеек и строк. Это включает шаблон строки, который копируется вместе с его контекстное меню, когда новые строки добавляются к элементу управления. Для обеспечения максимальной масштабируемости используйте только элемента управления <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойство, чтобы указать одно контекстное меню для всего элемента управления.  
  
-   Если требуется несколько контекстных меню для нескольких строк или ячеек, обрабатывать <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> или <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> события. Эти события позволяют управлять объектами контекстного меню самостоятельно, производя для настройки производительности.  
  
## <a name="using-automatic-resizing-efficiently"></a>Использование автоматического изменения размеров эффективно  
 Строк, столбцов и заголовков может автоматически изменяться при изменении содержимого ячеек так, чтобы отображались все содержимое ячейки без усечения. Изменение режима изменения размеров можно также изменить размеры строк, столбцов и заголовков. Для определения верного размера <xref:System.Windows.Forms.DataGridView> элемент управления должен проверить значение каждой ячейки, в нем. При работе с большими наборами данных, этот анализ может отрицательно повлиять на производительность элемента управления, при выполнении автоматического изменения размеров. Чтобы избежать потерь производительности, следуйте приведенным ниже рекомендациям:  
  
-   Старайтесь не использовать автоматическое изменение размеров на <xref:System.Windows.Forms.DataGridView> элемента управления с помощью большого набора строк. Если используется автоматическое изменение размеров только изменения размера на основе отображаемых строк. Используйте только те строки, отображаемой в виртуальном режиме, а также.  
  
    -   Для строк и столбцов, используйте `DisplayedCells` или `DisplayedCellsExceptHeaders` поле <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, и <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> перечисления.  
  
    -   Заголовки строк, используйте <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> или <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> поле <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> перечисления.  
  
-   Для обеспечения максимальной масштабируемости отключите автоматическое изменение размеров и использовать программного изменения размеров.  
  
 Дополнительные сведения см. в разделе [параметры изменения размера в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Эффективное использование выделенных ячеек, строк и столбцов коллекций  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> Коллекции, неэффективно с большой выбор. <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> И <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> также могут оказаться неэффективными, хотя и в меньшей степени, так как существует много меньше строк, чем ячеек в типичном <xref:System.Windows.Forms.DataGridView> управления и гораздо меньше столбцов, чем строк. Чтобы избежать снижения производительности при работе с этими коллекциями, следуйте приведенным ниже рекомендациям:  
  
-   Для определения ли все ячейки в <xref:System.Windows.Forms.DataGridView> были выбраны для доступа к содержимое <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> коллекции, проверьте значение, возвращаемое <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> метод. Обратите внимание, что этого метода может привести к строкам. Дополнительные сведения см. в следующем разделе.  
  
-   Избегайте использования <xref:System.Collections.ICollection.Count%2A> свойство <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> для определения числа выделенных ячеек. Вместо этого используйте <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> метод и передайте его в <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> значение. Аналогичным образом, использовать <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> методов, чтобы определить количество выбранных элементов, а не доступ к коллекциям выбранных строк и столбцов.  
  
-   Избегайте режимы выбора на основе ячеек. Вместо этого задайте <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Использование общих строк  
 Эффективного использования памяти производится в <xref:System.Windows.Forms.DataGridView> управление с помощью общих строк. Строки будут совместно использовать столько информации об их внешний вид и поведение можно путем совместного использования экземпляров <xref:System.Windows.Forms.DataGridViewRow> класса.  
  
 Пока совместное использование экземпляров строк сохраняет в памяти, строк можно легко строкам. Например каждый раз, когда пользователь взаимодействует непосредственно с ячейкой, соответствующей строке блокируется. Так как не удается избежать, приведенными в этом разделе полезны только при работе с очень большими объемами данных и только в том случае, если пользователи взаимодействуют с относительно небольшим часть данных при каждом запуске программы.  
  
 Строки не могут быть доступны несвязанного <xref:System.Windows.Forms.DataGridView> управления, если какие-либо ячейки, содержащие значение. Когда <xref:System.Windows.Forms.DataGridView> элемент управления привязан к внешнему источнику данных или при реализации виртуального режима и укажите источник данных, значения ячеек хранятся вне элемента управления, а не в объектах ячеек, что строк для совместного использования.  
  
 Объект строки можно использовать совместно только в том случае, если можно определить состояние всех его ячеек из состояния строки и состояний столбцов, содержащие ячейки. При изменении состояния ячейки, чтобы он больше не могут быть выведены от состояния ее строки и столбца, строки нельзя сделать общим.  
  
 Например строка не может использоваться в любом из следующих ситуаций:  
  
-   Строка содержит единственную выделенную ячейку, не находится в выбранном столбце.  
  
-   Строка содержит ячейку с его <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> или <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> набором свойств.  
  
-   Строка содержит <xref:System.Windows.Forms.DataGridViewComboBoxCell> с его <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> набор свойств.  
  
 В связанном или виртуальном режиме, вы можете предоставить подсказки и контекстные меню для отдельных ячеек, обрабатывая <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> и <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> события.  
  
 <xref:System.Windows.Forms.DataGridView> Управления автоматически будет пытаться использовать общие строки при добавлении строк в <xref:System.Windows.Forms.DataGridViewRowCollection>. Чтобы убедиться, что строки являются общими, следуйте приведенным ниже рекомендациям:  
  
-   Старайтесь не вызывать `Add(Object[])` перегруженная версия <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> метод и `Insert(Object[])` перегруженная версия <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> метод <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> коллекции. Эти перегрузки автоматически создают строки с монопольным доступом.  
  
-   Убедитесь, что строки, заданной в <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> свойства, которые могут использоваться в следующих случаях:  
  
    -   При вызове `Add()` или `Add(Int32)` перегрузок <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> метода или `Insert(Int32,Int32)` перегруженная версия <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> метод <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> коллекции.  
  
    -   Если увеличить значение <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> свойства.  
  
    -   При задании <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> свойство.  
  
-   Убедитесь, что к строке, указанной `indexSource` параметр можно использовать совместно, при вызове <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, и <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> методы <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> коллекции.  
  
-   Убедитесь, что при вызове может быть совместно указанной строки или строк `Add(DataGridViewRow)` перегруженная версия <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> метод, <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> метода `Insert(Int32,DataGridViewRow)` перегруженная версия <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> метода и <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> метод <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>коллекции.  
  
 Чтобы определить, является ли строка общей, используйте <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> метод для извлечения объекта строки и возврата объекта <xref:System.Windows.Forms.DataGridViewBand.Index%2A> свойство. Общие строки всегда имеют <xref:System.Windows.Forms.DataGridViewBand.Index%2A> значение свойства равно – 1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Предотвращение строкам  
 Общие строки может привести к блокированию кода или действия пользователя. Чтобы избежать снижения производительности, следует избегать, что приводит к строкам. Во время разработки приложения можно обрабатывать <xref:System.Windows.Forms.DataGridView.RowUnshared> событие, чтобы определить, когда строки становятся общими. Это полезно при отладке проблем общий доступ к строкам.  
  
 Чтобы предотвратить строк строкам, следуйте приведенным ниже рекомендациям:  
  
-   Следует избегать индексирования <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции или ее перебора с `foreach` цикла. Не потребуется обычно прямой доступ к строкам. <xref:System.Windows.Forms.DataGridView> методы, которые работают в строках принимают аргументы строки индекса, а не экземпляру строки. Кроме того обработчики событий, связанных со строками принимают аргумент объекты со свойствами строк, которые можно использовать для операций со строками, избегая их к строкам.  
  
-   Если необходимо получить доступ к объекту строки, используйте <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> метод и передайте ему фактический индекс строки. Обратите внимание, что для изменения объекта совместно используемой строки, полученные таким способом изменить все строки, которые совместно используют этот объект. Строку для новых записей не используется совместно с другими строками, тем не менее, так он не будут затронуты при изменении любых других строк. Обратите внимание, что различные строки, представленные совместно используемой строки могут иметь разные контекстные меню. Чтобы получить правильный контекстное меню из экземпляра общей строки, используйте <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> метод и передайте ему фактический индекс строки. Если доступ к совместно используемой строки <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> свойство вместо этого он будет использовать индекс совместно используемой строки-1 и не получает правильные контекстное меню.  
  
-   Следует избегать индексирования <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> коллекции. Для прямого доступа к ячейке приведет к ее родительской строки к строкам, создания нового <xref:System.Windows.Forms.DataGridViewRow>. Обработчики событий, связанных с ячейками принимают аргумент объекты со свойствами ячеек, которые можно использовать для операций с ячейками, не приводящее к строкам. Можно также использовать <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> свойства, чтобы получить индексы строки и столбца текущей ячейки без прямого доступа к ячейке.  
  
-   Избегайте режимы выбора на основе ячеек. Эти режимы привести к строкам. Вместо этого задайте <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   Не следует обрабатывать <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> события. Эти события привести к строкам. Кроме того, не следует вызывать <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> методы, которые инициируют эти события.  
  
-   Нет доступа к <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> коллекции при <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> значение свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, или <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. В этом случае все выделенные строки к строкам.  
  
-   Не вызывайте <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> метод. Использование этого метода может привести к строкам.  
  
-   Не вызывайте <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> метод при <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> значение свойства <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. В этом случае все строки к строкам.  
  
-   Не устанавливайте <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> или <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> свойство ячейки для `false` Если значение соответствующего свойства в столбце `true`. В этом случае все строки к строкам.  
  
-   Нет доступа к <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> свойство. В этом случае все строки к строкам.  
  
-   Не вызывайте `Sort(IComparer)` перегрузки <xref:System.Windows.Forms.DataGridView.Sort%2A> метод. Сортировка с помощью пользовательского модуля сравнения, все строки к строкам.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Изменение размеров управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
