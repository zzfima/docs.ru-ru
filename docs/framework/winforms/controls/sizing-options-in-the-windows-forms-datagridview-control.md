---
title: "Изменение размеров управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "таблицы данных, установка размеров столбцов"
  - "таблицы данных, установка размеров строк"
  - "таблицы данных, параметры изменения размера"
  - "DataGridView - элемент управления [Windows Forms], установка размеров столбцов"
  - "DataGridView - элемент управления [Windows Forms], установка размеров строк"
  - "DataGridView - элемент управления [Windows Forms], параметры изменения размера"
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Изменение размеров управления DataGridView в Windows Forms
Размер строк, столбцов и заголовков может изменяться <xref:System.Windows.Forms.DataGridView> во многих случаях.  В следующей таблице описаны условия, при которых происходит изменение размеров.  
  
|Условие|Описание|  
|-------------|--------------|  
|Изменение размеров пользователем|Пользователи могут изменять размеры при помощи перетаскивания или по двойному щелчку разделителей строки, столбца или заголовка.|  
|Изменение размеров элемента управления|В режиме заполнения столбца его ширина изменяется с изменением ширины элемента управления; например, когда элемент управления закреплен в родительской форме и пользователь изменяет размер формы.|  
|Изменение значения ячейки|В режимах автоматического изменения размеров в зависимости от содержимого, размеры изменяются таким образом, чтобы отобразить новые значения.|  
|Вызов метода|Изменение размеров в зависимости от программного содержимого позволяет в момент вызова метода добиться гибкой корректировки размеров в зависимости от значений в ячейке.|  
|Параметр свойства|Точные значения высоты и ширины можно установить.|  
  
 По умолчанию изменение размеров пользователем включено, а автоматическое изменение размеров отключено, и значения в ячейках, не помещающиеся в границах столбцов, обрезаются.  
  
 В следующей таблице показаны сценарии, которые можно использовать для изменения поведения по умолчанию; для достижения определенных эффектов можно использовать определенные параметры изменения размеров.  
  
|Сценарий|Реализация|  
|--------------|----------------|  
|Использование режима заполнения столбца для отображения данных с таким же размером в относительно небольшом числе столбцов, занимающих всю ширину элемента управления без отображения горизонтальной полосы прокрутки.|Установите для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.|  
|Использование режима заполнения столбца с отображением значений различных размеров.|Установите для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.  Инициализируйте относительную ширину столбцов, установив свойства <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> столбцов или вызвав метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> элемента управления после заполнения элемента управления данными.|  
|Использование режима заполнения со значениями различной важности.|Установите для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>.  Установите большие значения <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> для столбцов, в которых всегда должна отображаться часть данных, или для определенных столбцов используйте параметр изменения размера, отличный от режима заполнения.|  
|Использование режима заполнения столбца таким образом, чтобы фон элемента управления не отображался.|Присвойте свойству <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> последнего столбца значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> и используйте другие параметры изменения размеров для других столбцов.  Если другие столбцы занимают слишком большую часть доступного пространства, установите свойство <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> последнего столбца.|  
|Отображение столбца фиксированной ширины, например столбца со значком или идентификатором.|Свойству <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> присвойте значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>, свойству <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> — значение <xref:System.Windows.Forms.DataGridViewTriState> для столбца.  Инициализируйте его ширину, установив свойство <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> или вызвав метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> элемента управления после заполнения элемента управления данными.|  
|Автоматическое изменение размеров в случае изменения содержимого ячейки, чтобы исключить усечение и оптимизировать пространство.|Свойству автоматического изменения размеров присвойте значение, представляющее режим изменения размеров в соответствии с содержимым.  Чтобы избежать снижения производительности при работе с большими объемами данных, используйте режим изменения размеров, при котором рассчитываются только отображаемые строки.|  
|Изменение размеров в зависимости от значений в отображаемых строках так, чтобы избежать снижения производительности при работе с большим числом строк.|Используйте соответствующие значения перечисления режима изменения размеров с автоматическим или программным изменением размеров.  Чтобы подстроить размеры под значения во вновь отображаемых строках при прокрутке, вызовите метод изменения размеров в обработчике событий <xref:System.Windows.Forms.DataGridView.Scroll>.  Чтобы настроить изменение размеров при двойном щелчке пользователем так, чтобы только значения в отображаемых строках определяли новые размеры, вызовите метод изменения размеров в обработчике событий <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> или <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick>.|  
|Изменение размеров в зависимости от содержимого в ячейках только в определенные моменты времени так, чтобы исключить снижение производительности или задействовать изменение размеров пользователем.|Вызовите метод изменения размеров в зависимости от содержимого в обработчике событий.  Например, используйте событие <xref:System.Windows.Forms.DataGridView.DataBindingComplete> для инициализации размеров после привязки и обработайте событие <xref:System.Windows.Forms.DataGridView.CellValidated> или <xref:System.Windows.Forms.DataGridView.CellValueChanged>, чтобы скорректировать размеры для поправки на редактирование пользователем или изменения в связанном источнике данных.|  
|Изменение высоты строк для многострочного содержимого ячеек.|Удостоверьтесь, что ширина столбцов достаточна для отображения параграфов текста, или для изменения высоты используйте автоматическое или программное изменение размеров в зависимости от содержимого.  Также убедитесь, что ячейки с многострочным содержимым отображаются со значением стиля ячейки <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> равным <xref:System.Windows.Forms.DataGridViewTriState>.<br /><br /> Как правило, для сохранения ширины столбцов потребуется использовать режим автоматического изменения размеров столбцов или назначить им определенную ширину перед изменением высоты строк.|  
  
## Изменение размеров с помощью мыши  
 По умолчанию пользователи могут изменять размеры строк, столбцов и заголовков, для которых не используется режим автоматического изменения размеров в зависимости от значений в ячейках.  Чтобы пользователи не могли изменять размеры в других режимах, например в режиме заполнения столбцов, необходимо установить одно из следующих свойств <xref:System.Windows.Forms.DataGridView>:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Можно также запретить пользователям изменять размеры отдельных строк или столбцов, установив их значения <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>.  По умолчанию значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> основано на значении свойства <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> для столбцов и значении свойства <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> для строк.  Однако если для свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> явным образом установлено значение <xref:System.Windows.Forms.DataGridViewTriState> или <xref:System.Windows.Forms.DataGridViewTriState>, указанное значение переопределяет значение элемента управления для такой строки или столбца.  Чтобы восстановить наследование, свойству <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> необходимо присвоить значение <xref:System.Windows.Forms.DataGridViewTriState>.  
  
 Поскольку <xref:System.Windows.Forms.DataGridViewTriState> восстанавливает наследование значения, свойство <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> не будет возвращать значение <xref:System.Windows.Forms.DataGridViewTriState>, пока строка или столбец не будут добавлены в элемент управления <xref:System.Windows.Forms.DataGridView>.  Если необходимо установить, наследуется ли значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> для строки или столбца, проверьте свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A>.  Если значение <xref:System.Windows.Forms.DataGridViewElement.State%2A> содержит флаг <xref:System.Windows.Forms.DataGridViewElementStates>, значение свойства <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> не наследуется.  
  
## Автоматическое изменение размеров  
 Существует два типа автоматического изменения размеров в элементе управления <xref:System.Windows.Forms.DataGridView>: режим заполнения столбца и автоматическое изменение размеров в зависимости от содержимого.  
  
 В режиме заполнения столбца видимые столбцы в элементе управления заполняют ширину отображаемой области элемента управления.  Дополнительные сведения об этом режиме см. в разделе [Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Строки, столбцы и заголовки можно также настроить на автоматическое изменение размеров в зависимости от содержимого.  В этом случае размеры изменяются при каждом изменении содержимого ячейки.  
  
> [!NOTE]
>  Если значения ячеек хранятся в пользовательском кэше данных в виртуальном режиме, автоматическое изменение размеров происходит, когда пользователь редактирует значение ячейки, и не возникает, если значение в кэше изменяется вне обработчика событий <xref:System.Windows.Forms.DataGridView.CellValuePushed>.  В этом случае, необходимо вызвать метод <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> для принудительного обновления отображения ячейки элементом управления и применения текущих режимов автоматического изменения размеров.  
  
 Если автоматическое изменение размеров в зависимости от содержимого включено только для одного измерения, то есть для строк, а не столбцов или наоборот, и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> также включен, размер изменяется при каждом изменении другого измерения.  Например, если автоматическое изменение размеров настроено для строк, а не столбцов и режим <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> включен, пользователи смогут перетаскивать разделители столбцов, изменяя ширину столбца, и высота строк будет также изменяться автоматически таким образом, чтобы содержимое ячеек отображалось целиком.  
  
 Если автоматическое изменение размеров в зависимости от содержимого настроено как для столбцов, так и для строк и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> включен, размеры элемента управления <xref:System.Windows.Forms.DataGridView> будут изменяться каждый раз при изменении содержимого ячеек, и новые размеры будут рассчитываться на основе идеального соотношения высоты и ширины ячейки.  
  
 Чтобы настроить режим изменения размеров для заголовков и строк, а также для столбцов, которые не переопределяют значение элемента управления, установите одно или несколько свойств <xref:System.Windows.Forms.DataGridView>:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Чтобы переопределить режим изменения размеров столбца элемента управления для отдельного столбца, его свойству <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> следует присвоить значение, отличное от <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.  Режим изменения размеров для столбца фактически определяется его свойством <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>.  Значение этого свойства основано на значении свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> столбца, если оно не равно <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>, в случае чего наследуется значение <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> элемента управления.  
  
 При работе с большими объемами данных следует с осторожностью использовать автоматическое изменение размеров в зависимости от содержимого.  Во избежание снижения производительности используйте режимы автоматического изменения размеров, которые рассчитывают размеры только на основе отображаемых строк, а не посредством оценки каждой строки в элементе управления.  Для обеспечения максимальной производительности предпочтительней использовать программное изменение размеров, так чтобы изменять размеры можно было в определенное время, например сразу после загрузки новых данных.  
  
 Режимы автоматического изменения размеров на основе содержимого не затрагивают строки, столбцы или заголовки, которые скрыты путем установки свойства <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> строки или столбца, или свойств <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> или <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> элемента управления равным `false`.  Например, если столбец был скрыт после того, как его размер был автоматически изменен для вмещения большого значения ячейки, размер скрытого столбца не изменится, если удалить строку с большим значением ячейки.  Автоматическое изменение размеров не происходит при изменении режима видимости, поэтому изменение свойства <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> столбца на прежнее значение `true` не приведет к пересчету его размера на основе текущего содержимого.  
  
 Программное изменение размеров в зависимости от содержимого влияет на все строки, столбцы и заголовки независимо от их видимости.  
  
## Программное изменение размеров  
 Если автоматическое изменение размеров отключено, точную ширину или высоту строк, столбцов или заголовков можно установить программно при помощи следующих свойств:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>  
  
 Размер строк, столбцов и заголовков можно также программно изменить в соответствии с их содержимым с помощью следующих методов.  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Эти методы изменяют размеры строк, столбцов или заголовков один раз и не настроены на постоянное изменение размеров.  Новые размеры рассчитываются автоматически для отображения любого содержимого ячеек без усечения.  Однако если программно изменить размеры столбцов, значения свойства <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> которых равны <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>, полученные значения ширины согласно содержимому используются для пропорционального изменения значений свойства <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>, и фактические значения ширины столбцов затем рассчитываются по этим новым соотношениям, так что все столбцы заполняют доступную область отображения элемента управления.  
  
 Программное изменение размеров позволяет избежать снижения производительности при постоянном изменении размеров.  Это также позволяет задавать начальные размеры для строк, столбцов и заголовков, размеры которых может изменять пользователь, и подходит для режима заполнения столбца.  
  
 Методы программного изменения размеров, как правило, вызываются в определенные моменты времени.  Например, программно можно изменить размеры всех столбцов сразу после загрузки данных, или изменить размер заданной строки после изменения определенного значения ячейки.  
  
## Настройка поведения изменения размеров в зависимости от содержимого  
 Поведение изменения размеров можно настроить при работе с производными типами <xref:System.Windows.Forms.DataGridView>, ячейки, строки или столбца, переопределив методы <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=fullName>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=fullName> или вызвав защищенные перегрузки методов изменения размеров в производном элементе управления <xref:System.Windows.Forms.DataGridView>.  Защищенные перегрузки методов изменения размеров предназначены для работы в парах для достижения идеального соотношения высоты и ширины, исключая слишком широкие или высокие ячейки.  Например, если вызвать перегрузку `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` метода <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> и подставить значение `false` для параметра <xref:System.Boolean>, перегрузка рассчитает идеальную высоту и ширину для ячеек в строке, но изменит только высоту строк.  Затем нужно вызвать метод <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>, чтобы подстроить ширину столбцов под рассчитанное идеальное значение.  
  
## Параметры изменения размеров в зависимости от содержимого  
 Перечисления, используемые свойствами изменения размеров и методами, имеют одинаковые значения для изменения размеров в зависимости от содержимого.  Используя эти значения, можно ограничить ячейки, которые используются для вычисления предпочтительного размера.  Для всех перечислений изменения размеров значения с именами, относящимися к отображаемым ячейкам, ограничивают вычисления ячейками в отображаемых строках.  Исключение строк поможет избежать снижения производительности при работе с большим числом строк.  Вычисления можно также ограничить значениями ячеек в ячейках заголовка или других ячейках.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>   
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>   
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>   
 [Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)   
 [Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)