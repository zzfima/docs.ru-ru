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
ms.openlocfilehash: 6e3a7786970ef536da4ef7628cd33ae067ba90be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Изменение размеров управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> размер во многих случаях можно изменить строк, столбцов и заголовков. В следующей таблице показаны эти случаи.  
  
|Вхождение|Описание|  
|----------------|-----------------|  
|Изменение размеров пользователем|Пользователи могут изменять размеры, перетащив или дважды щелкнув разделителей строки, столбца или заголовка.|  
|Изменение размеров элемента управления|В режиме заполнения столбцов изменение ширины столбцов при изменении ширины элемента управления; Например, если элемент управления прикрепляется к родительской форме и пользователь изменяет размер формы.|  
|Изменение значения ячейки|В зависимости от содержимого режима автоматического изменения размеров размеры изменяются в соответствии с новыми значениями для отображения.|  
|Вызов метода|Программное изменение размеров на основе содержимого позволяет сделать гибкой корректировки размеров в зависимости от значения ячеек во время вызова метода.|  
|Значение свойства|Можно также задать значения определенных высоты и ширины.|  
  
 По умолчанию изменение размеров пользователем включено, отключено автоматическое изменение размеров и значения ячеек, которые шире, чем их столбцы будут обрезаны.  
  
 Ниже приведены сценарии, можно использовать для изменения поведения по умолчанию или параметры конкретного изменения размера для достижения таких эффектов, определенной.  
  
|Сценарий|Реализация|  
|--------------|--------------------|  
|Использование режима заполнения столбца для отображения с таким же размером данных в относительно небольшое число столбцов, занимающих всю ширину элемента управления без отображения горизонтальной полосы прокрутки.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Использование режима заполнения столбца с отображают значения различных размеров.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Инициализируйте относительную ширину столбцов путем присвоения столбцу <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> свойства или путем вызова элемента управления <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> метод после заполнения данными элемента управления.|  
|Используйте режим заполнения столбцов со значениями различной важности.|Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Значение велико <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> значения для столбцов, которые всегда должна отображаться часть данных или использовать параметр изменения размера, отличный от режима для определенных столбцов заполнения.|  
|Использование режима заполнения, чтобы избежать отображения фон элемента управления.|Задать <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> свойство столбца, чтобы <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> и использовать другие параметры изменения размера для других столбцов. Если другие столбцы с помощью слишком большого объема дискового пространства, задавать <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> свойства последнего столбца.|  
|Отобразите столбец фиксированной ширины, например значок или идентификатор столбца.|Задать <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> для <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> и <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> для <xref:System.Windows.Forms.DataGridViewTriState.False> для столбца. Инициализируйте его ширину, установив <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> свойства или путем вызова элемента управления <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> метод после заполнения данными элемента управления.|  
|Автоматическое изменение размеров всякий раз, когда изменения содержимого ячейки, чтобы исключить усечение и оптимизировать использование места.|Свойства автоматического изменения размеров в значение, представляющее режим изменения размера на основе содержимого. Чтобы избежать снижения производительности при работе с большими объемами данных, используйте режим изменения размера, которая вычисляет только отображаемые строки.|  
|Изменение размеров в зависимости от значений в отображаемых строк, чтобы избежать снижения производительности при работе с большим количеством строк.|Используйте соответствующее перечисление режим изменения размеров значения с автоматическое или программное изменение размеров. Чтобы изменить размеры под значения во вновь отображаемых строках при прокрутке, вызовите метод изменения размеров <xref:System.Windows.Forms.DataGridView.Scroll> обработчика событий. Для настройки, дважды щелкните пользователя изменения размера, чтобы только значения в отображаемых строк определения нового размера, вызовите метод изменения размеров <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> или <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> обработчика событий.|  
|Изменение размеров по содержимому ячеек только в определенное время, чтобы избежать снижения производительности или задействовать изменение размеров пользователем.|Вызовите метод изменения размеров на основе содержимого в обработчике событий. Например, использовать <xref:System.Windows.Forms.DataGridView.DataBindingComplete> событий для инициализации размеров после привязки и обработки <xref:System.Windows.Forms.DataGridView.CellValidated> или <xref:System.Windows.Forms.DataGridView.CellValueChanged> событий для контроля размера, чтобы компенсировать редактирование пользователем или изменения в связанном источнике данных.|  
|Изменение высоты строк для многострочного содержимого ячеек.|Убедитесь, что ширина столбцов достаточна для отображения абзацев текста и использовать для изменения высоты Установка размеров строк на основе содержимого автоматический или программный. Также убедитесь, что ячейки с многострочным содержимым отображаются с помощью <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> стиля значение из ячейки <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> Как правило для сохранения ширины столбцов или задать для них определенную ширину до высоты строк используется автоматический режим изменения размеров.|  
  
## <a name="resizing-with-the-mouse"></a>Изменение размеров с помощью мыши  
 По умолчанию пользователи могут изменять строк, столбцов и заголовков, которые не используют режим автоматического изменения размера на основе значений ячеек. Чтобы запретить пользователям изменять размеры в других режимах, такие как режим заполнения столбцов, задайте одно или несколько из следующих <xref:System.Windows.Forms.DataGridView> свойства:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Вы также можете запретить пользователям изменять размеры отдельных строк или столбцов, установив их <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> свойства. По умолчанию <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> зависит от значения свойства <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> значение свойства для столбцов и <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> значение свойства для строк. Если явно задать <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> для <xref:System.Windows.Forms.DataGridViewTriState.True> или <xref:System.Windows.Forms.DataGridViewTriState.False>, но при этом указанное значение переопределяет значение элемента управления для этой строки или столбца. Задать <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> для <xref:System.Windows.Forms.DataGridViewTriState.NotSet> для восстановления наследования.  
  
 Поскольку <xref:System.Windows.Forms.DataGridViewTriState.NotSet> восстанавливает наследование значения <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> не будет возвращать <xref:System.Windows.Forms.DataGridViewTriState.NotSet> пока строка или столбец не был добавлен к <xref:System.Windows.Forms.DataGridView> элемента управления. Если необходимо определить ли <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> унаследованные значения свойства строки или столбца, и проверьте его <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство. Если <xref:System.Windows.Forms.DataGridViewElement.State%2A> значение включает <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> флаг, <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> значение свойства не наследуется.  
  
## <a name="automatic-sizing"></a>Автоматическое изменение размеров  
 Существует два типа автоматического изменения размеров в <xref:System.Windows.Forms.DataGridView> управления: режим заполнения столбца и автоматическое изменение размеров в зависимости от содержимого.  
  
 Режим заполнения столбцов вызывает видимых столбцов в элементе управления заполняют ширину области отображения элемента управления. Дополнительные сведения об этом режиме см. в разделе [режим заполнения столбцов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Можно также настроить строк, столбцов и заголовков для автоматическое изменение размеров по содержимому их ячеек. В этом случае корректировку размера возникает при изменении содержимого ячейки.  
  
> [!NOTE]
>  Если ячейка значения хранятся в кэше пользовательских данных, в виртуальном режиме, автоматическое изменение размеров происходит, когда пользователь изменяет значение ячейки, но не возникает, если кэшированное значение за пределами <xref:System.Windows.Forms.DataGridView.CellValuePushed> обработчика событий. В этом случае вызов <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> способ принудительного обновления отображения ячейки и применение текущего режима автоматического изменения размеров элемента управления.  
  
 Если автоматическое изменение размеров в зависимости от содержимого включено только для одного измерения — — для строк, а не столбцов и для столбцов, но не строки — и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> является также включен, размер изменяется при каждом изменении другого измерения. Например, если строк, но не для столбцов, настроенных для автоматического изменения размеров и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> — включена, пользователи могут перетаскивать разделители столбцов, изменение ширины столбца и высоты строк автоматически изменяется так, чтобы по-прежнему полностью отображались содержимого ячейки.  
  
 При настройке строки и столбцы для автоматического изменения размеров в зависимости от содержимого и <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> включен, <xref:System.Windows.Forms.DataGridView> при каждом изменении содержимого ячейки и будут использовать соотношения высоты и ширины ячейки, когда новые размеры элемента управления будет изменение размеров.  
  
 Чтобы настроить режим изменения размеров для заголовков и строк и столбцов, которые не переопределяют значение элемента управления, установите одно или несколько из следующих <xref:System.Windows.Forms.DataGridView> свойства:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Чтобы переопределить режим изменения размеров столбца элемента управления для отдельного столбца, задайте его <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> свойство в значение, отличное от <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. Режим изменения размеров для столбца фактически определяется его <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> свойство. Значение этого свойства основан на столбце <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> значение свойства, если это значение не <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>в этом случае элемент управления <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> значение наследуется.  
  
 Используйте на основе содержимого автоматического изменения размера соблюдать осторожность при работе с большими объемами данных. Чтобы избежать снижения производительности, используйте режима автоматического изменения размеров, которые рассчитывают размеры только на основе отображаемых строк, а не посредством оценки каждой строки в элементе управления. Для обеспечения максимальной производительности используйте программное изменение размеров, так что вы можете изменить размер в определенное время, например сразу же после новых данных загружается.  
  
 Режима автоматического изменения размеров в зависимости от содержимого не влияют на строки, столбцы или заголовки, которые скрыты, задав строку или столбец <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> свойства или элемента управления <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> или <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> свойства `false`. Например если столбец скрыт после автоматическое изменение размеров по размеру большого значения ячейки, скрытого столбца не изменится его размер при удалении строки, содержащей большим значением ячейки. Автоматическое изменение размеров не происходит при изменении режима видимости, поэтому изменение столбца <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> обратно свойство `true` не приведет к пересчету его размера на основе текущего содержимого.  
  
 Программное изменение размеров на основе содержимого влияет на строки, столбцы и заголовки независимо от их видимости.  
  
## <a name="programmatic-resizing"></a>Программное изменение размеров  
 При отключении автоматического изменения размеров, можно программно установить точную ширину или высоту строк, столбцов или заголовков через следующие свойства:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Можно также программно изменить размер строк, столбцов и заголовков в соответствии с содержимым следующими способами:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Эти методы изменяют размеры строк, столбцов или один раз заголовки не настроены на постоянное изменение размеров. Новые размеры рассчитываются автоматически для отображения всего содержимого ячейки без усечения. Если программно изменить размеры столбцов, имеющих <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> значения свойств <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, однако рассчитанных значений ширины на основе содержимого, используются для пропорциональной регулировки столбец <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> фактически столбец, значения ширины и значений свойств затем вычисляется в соответствии с этим новым соотношениям, так что все столбцы заполняют доступную область отображения элемента управления.  
  
 Чтобы избежать снижения производительности при постоянном изменении размеров полезно программного изменения размеров. Также полезно для предоставления исходные размеры пользователь изменять размер строк, столбцов и заголовков и режима заполнения.  
  
 Обычно вы будете вызывать методы программного изменения размеров в определенные моменты времени. Например программно изменить размеры всех столбцов сразу после загрузки данных, или может программно изменить размеры конкретной строки после изменения определенного значения ячейки.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Настройка размеров на основе содержимого  
 Поведение размеров можно настроить при работе с производными <xref:System.Windows.Forms.DataGridView> типов ячеек, строк и столбцов путем переопределения <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, или <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> методы или вызвав защищенные перегрузки методов изменения размеров в производном <xref:System.Windows.Forms.DataGridView> элемент управления. Защищенные перегрузки методов изменения размеров предназначены для работы в парах для достижения соотношения высоты и ширины ячейки, как избежать чрезмерно ширину или высоту ячейки. Например, при вызове метода `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` перегруженная версия <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> метод и передайте его в значение `false` для <xref:System.Boolean> параметра перегрузка вычислит Идеальная высота и ширина ячейки в строке, но он будет изменение высоты строк только. Затем нужно вызвать <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> метод, чтобы ширина столбца изменялась в вычисляемые идеально подходит.  
  
## <a name="content-based-sizing-options"></a>Параметры изменения размера на основе содержимого  
 Перечисления, используемые свойствами изменения размеров и методы имеют одинаковые значения для изменения размера на основе содержимого. С этими значениями можно ограничить ячейки, которые используются для вычисления предпочтительного размера. Для всех перечислений изменения размеров значения с именами, относящимися к отображаемым ячейкам, ограничивают вычисления ячеек в отображаемых строк. За исключением строк, полезно избежать снижения производительности при работе с большим числом строк. Можно также ограничить вычисления значениями ячеек в ячейках заголовка или ячейки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Установка режимов заполнения для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
