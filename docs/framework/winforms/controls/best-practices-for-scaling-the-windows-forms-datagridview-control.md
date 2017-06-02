---
title: "Масштабирование элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "рекомендации, DataGridView - элемент управления"
  - "таблицы данных, рекомендации"
  - "DataGridView - элемент управления [Windows Forms], рекомендации"
  - "DataGridView - элемент управления [Windows Forms], общий доступ к строкам"
  - "DataGridView - элемент управления [Windows Forms], масштабирование"
  - "DataGridView - элемент управления [Windows Forms], общие строки"
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Масштабирование элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет обеспечить максимальную масштабируемость.  При необходимости отображения больших объемов данных следует придерживаться рекомендаций, приведенных в данном разделе, во избежание избыточного потребления памяти или замедления работы пользовательского интерфейса.  В этом разделе обсуждаются следующие вопросы:  
  
-   эффективное использование стилей ячеек;  
  
-   эффективное использование контекстных меню;  
  
-   эффективное использование автоматического изменения размеров;  
  
-   эффективное использование коллекций выбранных ячеек, строк и столбцов;  
  
-   использование общих строк;  
  
-   предотвращение блокирования общего доступа к строкам.  
  
 Если предъявляются особые требования к производительности, можно реализовать виртуальный режим и обеспечить выполнение особых операций по управлению данными.  Дополнительные сведения см. в разделе [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## Эффективное использование стилей ячеек  
 Каждая ячейка, строка и столбец может иметь сведения о стиле.  Сведения о стиле хранятся в объектах <xref:System.Windows.Forms.DataGridViewCellStyle>.  Создание объектов стиля ячеек для большого числа элементов <xref:System.Windows.Forms.DataGridView> может оказаться неэффективным, особенно при работе с большими объемами данных.  Чтобы избежать снижения производительности, воспользуйтесь следующими рекомендациями.  
  
-   Избегайте задания стиля ячеек для каждого отдельного объекта <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewRow>.  Это относится и к объектам строки, определяемым свойством <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  Объект стиля ячеек, связанный с шаблоном строк, будет копироваться для каждой новой строки, создаваемой на основе шаблона.  Для обеспечения максимальной масштабируемости следует задавать свойства стиля ячеек на уровне <xref:System.Windows.Forms.DataGridView>.  Так, задание свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> следует предпочесть заданию свойства <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>.  
  
-   Если для некоторых ячеек требуется форматирование, отличное от форматирования по умолчанию, используйте один экземпляр <xref:System.Windows.Forms.DataGridViewCellStyle> для групп ячеек, строк или столбцов.  Избегайте прямого задания свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle> для отдельных ячеек, строк и столбцов.  Пример совместного использования стиля ячеек см. в разделе [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Избежать потери производительности, связанной с заданием стиля ячеек по отдельности, можно путем обработки события <xref:System.Windows.Forms.DataGridView.CellFormatting>.  Пример см. в разделе [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   При определении стиля ячейки свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName> следует предпочесть  свойству <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>.  Если свойство <xref:System.Windows.Forms.DataGridViewCell.Style%2A> ранее не использовалось, то при обращении к нему создается новый экземпляр класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  Кроме того, сведения о стиле ячейки, содержащиеся в этом объекте, могут быть неполными, если некоторые стили наследуются от строк, столбцов или элементов управления.  Дополнительные сведения о наследовании стилей ячеек см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Эффективное использование контекстных меню  
 Каждая ячейка, строка и столбец может иметь собственное контекстное меню.  Контекстные меню в элементе управления <xref:System.Windows.Forms.DataGridView> представлены элементами управления <xref:System.Windows.Forms.ContextMenuStrip>.  Так же как и в случае с объектами стиля ячеек, создание контекстных меню для множества отдельных элементов <xref:System.Windows.Forms.DataGridView> может отрицательно сказаться на производительности.  Чтобы избежать потерь производительности, воспользуйтесь следующими рекомендациями.  
  
-   Избегайте создания контекстных меню для отдельных ячеек или строк.  Это относится и к шаблону строк, который копируется вместе с контекстным меню при добавлении в элемент управления новых строк.  Для обеспечения максимальной масштабируемости используйте только свойство <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> элемента управления, чтобы определить для него единое контекстное меню.  
  
-   Если необходимо создать несколько контекстных меню для разных строк или ячеек, прибегните к обработке событий <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> или <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>.  Эти события позволяют управлять объектами контекстного меню самостоятельно, производя соответствующую настройку производительности.  
  
## Эффективное использование автоматического изменения размеров  
 Размеры строк, столбцов и заголовков могут изменяться автоматически при изменении содержимого ячеек так, чтобы значения ячеек могли отображаться в них без усечения.  Изменение размеров строк, столбцов и заголовков может также осуществляться за счет изменения режимов изменения размеров.  Для правильного определения размеров элемент управления <xref:System.Windows.Forms.DataGridView> должен проверить значение каждой содержащейся в нем ячейки.  При работе с большими объемами данных эта проверка может отрицательно сказаться на производительности элемента управления при выполнении автоматического изменения размеров.  Чтобы избежать потерь производительности, воспользуйтесь следующими рекомендациями.  
  
-   Избегайте использования автоматического изменения размеров, если элемент <xref:System.Windows.Forms.DataGridView> содержит большое количество строк.  Если автоматическое изменение размеров все же используется, применяйте его только к отображаемым строкам.  Виртуальный режим также следует применять только к отображаемым строкам.  
  
    -   Для строк и столбцов используйте поле `DisplayedCells` или `DisplayedCellsExceptHeaders` перечислений <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> и <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.  
  
    -   Для заголовков строк используйте поле <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> или <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> перечисления <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>.  
  
-   Для обеспечения максимальной масштабируемости отключите автоматическое изменение размеров и воспользуйтесь программным изменением размеров.  
  
 Дополнительные сведения см. в разделе [Изменение размеров управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## Эффективное использование коллекций выбранных ячеек, строк и столбцов  
 Коллекция <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> обладает низкой эффективностью при выделении большого числа ячеек.  Коллекции <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> также могут оказаться неэффективными, хотя и в меньшей степени, поскольку обычно элемент управления <xref:System.Windows.Forms.DataGridView> имеет гораздо меньше строк, чем ячеек, и гораздо меньше столбцов, чем строк.  Чтобы избежать потерь производительности при работе с этими коллекциями, воспользуйтесь следующими рекомендациями.  
  
-   Чтобы определить, были ли выделены все ячейки элемента управления <xref:System.Windows.Forms.DataGridView>, перед тем как получить доступ к содержимому коллекции <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, необходимо проверить значение, возвращаемое методом <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>.  Следует обратить внимание, однако, что этот метод может заблокировать общий доступ к строкам.  Дополнительные сведения см. в следующем разделе.  
  
-   Избегайте использования свойства <xref:System.Collections.ICollection.Count%2A> коллекции <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=fullName> для определения числа выделенных ячеек.  Вместо этого воспользуйтесь методом <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=fullName>, которому следует передать значение свойства <xref:System.Windows.Forms.DataGridViewElementStates?displayProperty=fullName>.  Аналогичным образом, для определения числа выделенных элементов следует воспользоваться методами <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=fullName> и <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=fullName> вместо обращения к коллекциям выделенных строк и столбцов.  
  
-   Избегайте использования режимов выделения на уровне ячеек.  Вместо этого установите свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> равным <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>.  
  
## Использование общих строк  
 Применение общих строк в элементе управления <xref:System.Windows.Forms.DataGridView> позволяет добиться эффективного использования памяти.  За счет совместного использования экземпляров класса <xref:System.Windows.Forms.DataGridViewRow> строки будут иметь максимальное количество общих сведений о внешнем виде и поведении.  
  
 Совместное использование экземпляров строк позволяет экономить память, однако общий доступ к строкам зачастую блокируется.   Например, при прямом взаимодействии пользователя с ячейкой, общий доступ к соответствующей строке блокируется.  Поскольку избежать этого невозможно, рекомендации, приводимые в данном разделе, целесообразно использовать только при работе с очень большими объемами данных, и только если пользователи взаимодействуют только с относительно небольшой долей данных при каждом запуске приложения.  
  
 Если какие\-либо ячейки несвязанного элемента управления <xref:System.Windows.Forms.DataGridView> содержат значения, строку невозможно сделать общей.  При привязке элемента управления <xref:System.Windows.Forms.DataGridView> к к внешнему источнику данных или предоставлении собственного источника данных путем реализации виртуального режима значения ячеек хранятся не в объектах ячеек, а вне элемента управления, что позволяет обеспечить совместное использование строк.  
  
 Совместное использование объекта строки допустимо допустимо только в том случае, если состояние всех его ячеек можно определить на основании состояния строки и состояний столбцов, к которым относятся ячейки.  Если после изменения состояния ячейки, оно не может быть определено, исходя из состояния соответствующей строки и столбца, совместное использование строки невозможно.  
  
 Так, строка не может являться общей в следующих ситуациях.  
  
-   Строка содержит единственную выделенную ячейку, не входящую в выделенный столбец.  
  
-   Строка содержит ячейку с заданными свойствами <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> или <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A>.  
  
-   Строка содержит <xref:System.Windows.Forms.DataGridViewComboBoxCell> с заданными свойством <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A>.  
  
 В связанном или виртуальном режимах элементы ToolTips или контекстные меню для отдельных ячеек можно обеспечить путем обработки событий <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> и <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>.  
  
 При добавлении строк в коллекцию <xref:System.Windows.Forms.DataGridViewRowCollection> элемент управления <xref:System.Windows.Forms.DataGridView> будет автоматически пытаться использовать общие строки.  Чтобы обеспечить совместное использование строк, воспользуйтесь следующими рекомендациями.  
  
-   Избегайте вызовов перегрузки `Add(Object[])` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> и перегрузки `Insert(Object[])` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  Эти перегрузки автоматически создают строки с запрещением общего доступа.  
  
-   Убедитесь, что к строке, определяемой свойством <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>, возможен общий доступ, в следующих случаях.  
  
    -   При вызове перегрузок `Add()` или `Add(Int32)` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, либо перегрузки `Insert(Int32,Int32)` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
    -   При увеличении значения свойства <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=fullName>.  
  
    -   При задании свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>.  
  
-   Убедитесь в том, что к строке, указанной в параметре `indexSource`, возможен общий доступ, при вызове методов <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> и <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
-   Убедитесь в том, что к указанной строке или строкам возможен общий доступ, при вызове перегрузки `Add(DataGridViewRow)` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, метода <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>, перегрузки `Insert(Int32,DataGridViewRow)` метода <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> и метода <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
 Чтобы определить является ли строка общей, воспользуйтесь методом <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> для извлечения объекта строки и затем проверьте свойство <xref:System.Windows.Forms.DataGridViewBand.Index%2A> полученного объекта.  Для общих строк значение свойства <xref:System.Windows.Forms.DataGridViewBand.Index%2A> всегда равно –1.  
  
## Предотвращение блокирования общего доступа к строкам  
 Выполнение кода или действия пользователя могут привести к блокированию общего доступа к строкам.  Этого следует избегать в целях обеспечения оптимальной производительности.  В процессе разработки приложения блокирование общего доступа к строкам можно реализовать путем обработки события <xref:System.Windows.Forms.DataGridView.RowUnshared>.  Это может быть полезно при отладке неисправностей, связанных с общим доступом к строкам.  
  
 Чтобы избежать блокирования общего доступа к строкам, воспользуйтесь следующими рекомендациями.  
  
-   Избегайте индексирования коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A> или ее перебора с помощью оператора цикла `foreach`.  Обычно не возникает необходимости в прямом доступе к строкам.  Методы <xref:System.Windows.Forms.DataGridView>, оперирующие со строками, принимают в качестве аргумента индексы строк, а не их экземпляры.  Кроме того, обработчики событий, связанных со строками, принимают в качестве аргументов объекты со свойствами строк, которые можно использовать для операций со строками, не блокируя общий доступ к ним.  
  
-   Если необходимо получить доступ к объекту строки, воспользуйтесь методом <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> и передайте ему фактический индекс строки.  Однако следует обратить внимание, что изменение объекта общей строки, полученного с помощью данного метода, приведет к изменению всех строк, совместно использующих данный объект.  Строка для добавления новых записей не допускает использования общего доступа, следовательно изменение других строк не окажет на нее воздействия.  Следует также обратить внимание, что различные строки, представленные общей строкой, могут иметь разные контекстные меню.  Чтобы извлечь соответствующее контекстное меню из экземпляра общей строки, воспользуйтесь методом <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> и передайте ему фактический индекс строки.  При попытке доступа к свойству <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> общей строки будет использован индекс общей строки, равный \-1, и получено неправильное контекстное меню.  
  
-   Избегайте индексации коллекции <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=fullName>.  Прямое обращение к ячейке приведет к блокированию общего доступа к родительской строке и созданию нового объекта <xref:System.Windows.Forms.DataGridViewRow>.  Обработчики событий, связанных с ячейками, принимают в качестве аргументов объекты со свойствами ячеек, которые можно использовать для операций с ячейками, не блокируя общий доступ к строкам.  Чтобы извлечь индексы строки и столбца текущей ячейки, не обращаясь напрямую к ячейке, можно также воспользоваться свойством <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A>.  
  
-   Избегайте использования режимов выделения на уровне ячеек.  Эти режимы могут заблокировать общий доступ к строкам.  Вместо этого установите свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> равным <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>.  
  
-   Не обрабатывайте события <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=fullName>.  Эти события могут заблокировать общий доступ к строкам.  Не следует также вызывать методы <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=fullName>, которые инициируют эти события.  
  
-   Не обращайтесь к коллекции <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=fullName>, если свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> имеет значения <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode> или <xref:System.Windows.Forms.DataGridViewSelectionMode>.  При этом будет заблокирован общий доступ ко всем выделенным строкам.  
  
-   Не вызывайте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=fullName>.  Этот метод может заблокировать общий доступ к строкам.  
  
-   Не вызывайте метод <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=fullName>, если свойство <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode>.  При этом будет заблокирован общий доступ ко всем выделенным строкам.  
  
-   Не следует присваивать свойствам <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> или <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> ячейки значение `false`, если соответствующее свойство столбца имеет значение `true`.  При этом будет заблокирован общий доступ ко всем выделенным строкам.  
  
-   Не обращайтесь к свойству <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=fullName>.  При этом будет заблокирован общий доступ ко всем выделенным строкам.  
  
-   Не вызывайте перегрузку `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>.  При использовании пользовательской функции сравнения будет заблокирован общий доступ ко всем выделенным строкам.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Изменение размеров управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)