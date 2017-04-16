---
title: "Стили ячеек элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, стили"
  - "таблицы данных, стили ячеек"
  - "DataGridView - элемент управления [Windows Forms], стили ячеек"
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Стили ячеек элемента управления DataGridView в Windows Forms
Каждая ячейка в элементе управления <xref:System.Windows.Forms.DataGridView> может иметь собственный стиль, включая формат текста, цвет фона, основной цвет и шрифт.  Впрочем, обычно несколько ячеек обладают одинаковым стилем.  
  
 Группы ячеек с одинаковым стилем могут включать все ячейки в определенных строках или столбцах, все ячейки с определенными значениями или все ячейки в элементе управления.  Эти группы могут пересекаться, поэтому каждая ячейка может получать данные своего стиля из нескольких источников.  Например, может потребоваться, чтобы во всех ячейках элемента управления <xref:System.Windows.Forms.DataGridView> использовался одинаковый шрифт, но чтобы только столбцах, где содержатся денежные значения, использовался формат денежных единиц, и чтобы в ячейках денежных единиц, содержащих отрицательные значения, основной цвет был красным.  
  
## Класс DataGridViewCellStyle  
 Класс <xref:System.Windows.Forms.DataGridViewCellStyle> содержит следующие свойства, относящиеся к стилю:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Этот класс также содержит следующие свойства, связанные с форматированием:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Дополнительные сведения об этих свойствах и других свойствах стилей ячеек см. в справочной документации <xref:System.Windows.Forms.DataGridViewCellStyle> и в разделах, перечисленных в главе "См. также" ниже.  
  
## Использование объектов DataGridViewCellStyle  
 Можно извлекать объекты <xref:System.Windows.Forms.DataGridViewCellStyle> из различных свойств классов <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> и <xref:System.Windows.Forms.DataGridViewCell>, а также производных классов.  Если одно из этих свойств еще не указано, при получении его значения будет создан новый объект <xref:System.Windows.Forms.DataGridViewCellStyle>.  Также можно создать экземпляры собственных объектов <xref:System.Windows.Forms.DataGridViewCellStyle> и назначить их этим свойствам.  
  
 Можно избежать ненужного дублирования данных стилей путем общего доступа к объектам <xref:System.Windows.Forms.DataGridViewCellStyle> между несколькими элементами <xref:System.Windows.Forms.DataGridView>.  Стили, указанные на уровне элемента управления, столбца и строки, применяются ко всем нижележащим уровням вплоть до уровня ячейки, можно избежать дублирования стилей, указывая на каждом уровне только те свойства стилей, которые отличаются от указанных на более высоких уровнях.  Это описано более подробно в следующем разделе "Наследование стилей".  
  
 В следующей таблице перечислены основные свойства, получающие или устанавливающие объекты <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
|Свойство.|Классы|Описание|  
|---------------|------------|--------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> и производные классы|Получает или устанавливает стили по умолчанию, используемые всеми ячейками во всем элементе управления \(включая заголовки\), в столбце или в строке.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Получает или устанавливает стили ячеек по умолчанию, используемые во всех строках элемента управления.  Это не относится к ячейкам заголовков.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Получает или устанавливает стили ячеек по умолчанию, используемые во чередующихся строках элемента управления.  Это позволяет задать один стиль для четных строк, а другой — для нечетных.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Получает или устанавливает стили ячеек по умолчанию, используемые в заголовках строк элемента управления.  Эти параметры заменяются текущей темой, если включены наглядные стили.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Получает или устанавливает стили ячеек по умолчанию, используемые в заголовках столбцов элемента управления.  Эти параметры заменяются текущей темой, если включены наглядные стили.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> и производные классы|Получает или устанавливает стили на уровне ячейки.  Эти стили заменяют стиль, унаследованный с более высоких уровней.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn> и производные классы|Получает все стили, примененные в настоящий момент к ячейке, строке или столбцу, включая унаследованные стили.|  
  
 Как было сказано выше, при получении значения свойства стиля автоматически создается новый экземпляр объекта <xref:System.Windows.Forms.DataGridViewCellStyle>, если свойство не было указано ранее.  Чтобы избежать создания этих объектов без необходимости, в классах строк и столбцов есть свойство <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A>, которое можно проверить, чтобы узнать, установлено ли свойство <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>.  Сходным образом, в классах ячеек есть свойство <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A>, указывающее, установлено ли свойство <xref:System.Windows.Forms.DataGridViewCell.Style%2A>.  
  
 Для каждого свойства стиля есть соответствующее событие *ИмяСвойства*`Changed` в элементе управления <xref:System.Windows.Forms.DataGridView>.  Для свойств строк, столбцов и ячеек имя события начинается с "`Row`", "`Column`" или "`Cell`" \(например, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>\).  Каждое из этих событий происходит, когда соответствующее свойство стиля устанавливается для другого объекта <xref:System.Windows.Forms.DataGridViewCellStyle>.  Эти события не происходят при получении объекта <xref:System.Windows.Forms.DataGridViewCellStyle> из свойства стиля и изменении значений его свойств.  Для реагирования на изменения самих объектов стиля ячейки требуется обработка события <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>.  
  
## Наследование стиля  
 Каждая ячейка <xref:System.Windows.Forms.DataGridViewCell> получает данные о своем внешнем виде из свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  Объект <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемый этим свойством, наследует свои значение от иерархии свойств типа <xref:System.Windows.Forms.DataGridViewCellStyle>.  Эти свойства перечислены ниже в порядке, в котором получает свои значения <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> для ячеек, не находящихся в заголовках.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(только для ячеек в нечетных строках\)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Для ячеек заголовков столбцов и строк свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> заполняется значениями из следующего списка исходных свойств в данном порядке.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Этот процесс показан на следующей схеме.  
  
 ![Свойства типа DataGridViewCellStyle](../../../../docs/framework/winforms/controls/media/datagridviewcells1.png "DataGridViewCells1")  
  
 Также можно получить доступ к стилям, унаследованным определенными строками и столбцами.  Свойство столбца <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> наследует значения от следующих свойств.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Свойство строки <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> наследует значения от следующих свойств.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(только для ячеек в нечетных строках\)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Для каждого свойства в объекте <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращенном свойством `InheritedStyle`, значение свойства берется из первого стиля ячейки в соответствующем списке, в котором значение свойства отличается от значения по умолчанию для класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 В следующей таблице показано наследование значения свойства <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> ячейки от столбца, в котором находится эта ячейка.  
  
|Свойство типа `DataGridViewCellStyle`|Пример значения `ForeColor` для полученного объекта|  
|-------------------------------------------|---------------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Red%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Black%2A?displayProperty=fullName>|  
  
 В этом случае значение <xref:System.Drawing.Color.Red%2A?displayProperty=fullName> из строки ячейки является первым действительным значением в списке.  Оно становится значением свойства <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> стиля ячейки <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 На следующей схеме показано, как различные свойства <xref:System.Windows.Forms.DataGridViewCellStyle> могут наследовать значения из различных источников.  
  
 ![Наследование значений свойств DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewcells2.png "DataGridViewCells2")  
  
 Используя наследование стилей можно предоставить соответствующие стили для всего элемента управления, не указывая одинаковую информацию несколько раз.  
  
 Ячейки заголовка участвуют в описанном наследовании стиля, однако объекты, возвращенные свойствами <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView>, имеют начальные значения, которые заменяют значения объекта, возвращенные свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>.  Если требуется, чтобы свойства объекта, возвращаемые свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, применялись к заголовкам строк и столбцов, нужно установить для соответствующих поставщиков объектов, возвращаемых свойствами <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>, значения по умолчанию, указанные для класса <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
> [!NOTE]
>  Если включены наглядные стили, то заголовки строк и столбцов \(кроме <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) автоматически получают стиль текущей темы, заменяя все стили, указанные для этих свойств.  
  
 Типы <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn> и <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> также инициализируют некоторые значения объекта, возвращенного свойством столбца <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>.  Дополнительные сведения см. в справочной документации для этих типов.  
  
## Динамическая установка стилей  
 Чтобы настроить стиль ячеек с использованием определенных значений, реализуйте обработчик для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  Обработчики этого события получают аргумент типа <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>.  Этот объект содержит свойства, позволяющие определить значение форматируемой ячейки, а также ее расположение в элементе управления <xref:System.Windows.Forms.DataGridView>.  Этот объект также содержит свойство <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A>, которое при инициализации получает значение свойства <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> форматируемой ячейки.  Можно изменить свойства стиля ячейки и указать данные стиля в соответствии со значением ячейки и ее расположением.  
  
> [!NOTE]
>  События <xref:System.Windows.Forms.DataGridView.RowPrePaint> и <xref:System.Windows.Forms.DataGridView.RowPostPaint> также получают объект <xref:System.Windows.Forms.DataGridViewCellStyle> в данных события, но в этом случае это копия свойства строки <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>, доступная только для чтения; ее изменения не влияют на элемент управления.  
  
 Кроме того, можно динамически изменять стили определенных ячеек на основе событий, таких как <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=fullName> и <xref:System.Windows.Forms.DataGridView.CellMouseLeave>.  Например, в обработчике события <xref:System.Windows.Forms.DataGridView.CellMouseEnter> можно хранить текущее значение фонового цвета ячейки \(это значение можно получить посредством свойства <xref:System.Windows.Forms.DataGridViewCell.Style%2A>\), затем можно установить новый цвет, которым ячейка будет выделена при наведении на нее указателя мыши.  После этого в обработчике события <xref:System.Windows.Forms.DataGridView.CellMouseLeave> можно вернуть исходный цвет фона.  
  
> [!NOTE]
>  Вне зависимости от того, указано ли то или иное значение стиля, следует обратить внимание на кэширование значений, хранящихся в свойстве <xref:System.Windows.Forms.DataGridViewCell.Style%2A>.  Если временно заменить параметр стиля, возврат его в исходное "неопределенное" состояние приведет к тому, что ячейка снова будет наследовать этот параметр стиля с более высокого уровня.  Если нужно определить текущий стиль, действующий для ячейки независимо от наследуемого стиля, используйте свойство <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)