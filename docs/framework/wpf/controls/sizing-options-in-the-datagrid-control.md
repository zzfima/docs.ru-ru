---
title: "Параметры изменения размеров элемента управления DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "автоматическое определение размера DataGrid"
  - "DataGrid - элемент управления [WPF], установка размеров"
  - "размер [WPF], DataGrid"
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Параметры изменения размеров элемента управления DataGrid
Для управления способом, с помощью которого элемент управления <xref:System.Windows.Controls.DataGrid> изменяет свой размер, доступны различные параметры.  Для размеров элемента управления <xref:System.Windows.Controls.DataGrid> и отдельных строк и столбцов <xref:System.Windows.Controls.DataGrid> можно задать конкретные значения или установить их автоматическое изменение в соответствии с содержимым элемента управления.  По умолчанию <xref:System.Windows.Controls.DataGrid> будет увеличиваться и уменьшаться в соответствии с размером его содержимого.  
  
## Задание размера DataGrid  
  
### Предостережения при использовании автоматического изменения размеров  
 По умолчанию для свойств <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> элемента управления <xref:System.Windows.Controls.DataGrid> задается значение <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" в XAML\) и размер <xref:System.Windows.Controls.DataGrid> будет настроен в соответствии с содержимым этого элемента управления.  
  
 При размещении внутри контейнера, не ограничивающего размер своих дочерних элементов, например <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.StackPanel>, элемент управления <xref:System.Windows.Controls.DataGrid> будет растягиваться за пределы видимых границ контейнера без отображения полос прокрутки.  Это условие имеет негативные последствия для удобства использования и производительности.  
  
 Если при привязке к набору данных значение свойства <xref:System.Windows.FrameworkElement.Height%2A> элемента управления <xref:System.Windows.Controls.DataGrid> не ограничено, элемент управления продолжит добавление строк для каждого элемента данных из привязанного набора данных.  Это может привести к увеличению элемента управления <xref:System.Windows.Controls.DataGrid> за пределы видимых границ приложения по мере добавления строк.  В этом случае элемент управления <xref:System.Windows.Controls.DataGrid> не будет отображать полосы прокрутки, поскольку его свойство <xref:System.Windows.FrameworkElement.Height%2A> продолжит увеличение в соответствии с новыми строками.  
  
 Для каждой строки элемента управления <xref:System.Windows.Controls.DataGrid> создается объект.  Если при работе с большим набором данных разрешено автоматическое изменение размера элемента управления <xref:System.Windows.Controls.DataGrid>, создание большого числа объектов может повлиять на производительность приложения.  
  
 Чтобы избежать этих проблем при работе с большими наборами данных, рекомендуется задать конкретное значение для свойства <xref:System.Windows.FrameworkElement.Height%2A> элемента управления <xref:System.Windows.Controls.DataGrid> или поместить этот элемент управления в контейнер, который ограничит значение его свойства <xref:System.Windows.FrameworkElement.Height%2A>, например <xref:System.Windows.Controls.Grid>.  При ограничении значения свойства <xref:System.Windows.FrameworkElement.Height%2A> элемент управления <xref:System.Windows.Controls.DataGrid> создает только такое количество строк, которое будет умещаться по высоте, заданной значением свойства <xref:System.Windows.FrameworkElement.Height%2A>, и будет повторно использовать эти строки для новых данных.  
  
### Задание размера DataGrid  
 Можно установить автоматическое изменение размеров <xref:System.Windows.Controls.DataGrid> в пределах указанных границ или задать для <xref:System.Windows.Controls.DataGrid> фиксированные размеры.  В следующей таблице приведены свойства, которые можно задавать для управления размером <xref:System.Windows.Controls.DataGrid>.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Задает определенную высоту <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Задает верхнюю границу высоты <xref:System.Windows.Controls.DataGrid>.  Элемент управления <xref:System.Windows.Controls.DataGrid> увеличивается по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Задает нижнюю границу высоты <xref:System.Windows.Controls.DataGrid>.  Элемент управления <xref:System.Windows.Controls.DataGrid> уменьшается по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Задает определенную ширину <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Задает верхнюю границу ширины <xref:System.Windows.Controls.DataGrid>.  Элемент управления <xref:System.Windows.Controls.DataGrid> увеличивается по горизонтали до достижения этой ширины.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Задает нижнюю границу ширины <xref:System.Windows.Controls.DataGrid>.  Элемент управления <xref:System.Windows.Controls.DataGrid> уменьшается по горизонтали до достижения этой ширины.|  
  
## Изменение размеров строк и заголовков строк  
  
### Строки DataGrid  
 По умолчанию для свойства <xref:System.Windows.FrameworkElement.Height%2A> строки <xref:System.Windows.Controls.DataGrid> задается значение <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" в XAML\) и высота строки будет увеличиваться в соответствии с размером ее содержимого.  Можно указать высоту всех строк в элементе управления <xref:System.Windows.Controls.DataGrid>, задав свойство <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=fullName>.  Пользователи могут изменять высоту строк путем перетаскивания разделителей заголовков строк.  
  
### Заголовки строк DataGrid  
 Для отображения заголовков строк нужно установить для свойства <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> значение <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> или <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>.  По умолчанию заголовки строк отображаются и их размер автоматически изменяется в соответствии с содержимым.  Можно установить фиксированную ширину заголовков строк, задав значение свойства <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=fullName>.  
  
## Изменение размеров столбцов и заголовков столбцов  
  
### Столбцы DataGrid  
 Для указания абсолютного или автоматического режима изменения размеров в элементе <xref:System.Windows.Controls.DataGrid> используются значения объекта <xref:System.Windows.Controls.DataGridLength> и структуры <xref:System.Windows.Controls.DataGridLengthUnitType>.  
  
 В следующей таблице показаны значения, предоставляемые структурой <xref:System.Windows.Controls.DataGridLengthUnitType>.  
  
|Имя|Описание|  
|---------|--------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|В режиме автоматического изменения размеров по умолчанию размеры столбцов <xref:System.Windows.Controls.DataGrid> изменяются в соответствии с содержимым ячеек и заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|В режиме автоматического изменения размеров на основе ячеек размеры столбцов <xref:System.Windows.Controls.DataGrid> изменяются в зависимости от содержимого ячеек в столбце, исключая заголовки столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|В режиме автоматического изменения размеров на основе заголовков размеры столбцов <xref:System.Windows.Controls.DataGrid> изменяются в зависимости от содержимого только заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|В режиме изменения размеров на основе пикселей размер столбцов <xref:System.Windows.Controls.DataGrid> определяется указанным числовым значением.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Режим изменения размера "звездочка" используется для пропорционального распределения доступного места.<br /><br /> В языке XAML значения "звездочка" выражаются в виде "n\*", где "n" представляет числовое значение.  "1\*" является эквивалентом "\*".  Например, если два столбца элемента управления <xref:System.Windows.Controls.DataGrid> имеют ширину "\*" и "2\*", первый столбец получит одну часть доступного места, а второй столбец получит две части доступного места.|  
  
 Для преобразования данных между числовыми или строковыми значениями и значениями <xref:System.Windows.Controls.DataGridLength> может использоваться класс <xref:System.Windows.Controls.DataGridLengthConverter>.  
  
 По умолчанию свойства <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName> задано значение <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>, а для свойства <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName> — значение <xref:System.Windows.Controls.DataGridLength.Auto%2A>.  Если для режима изменения размеров задано значение <xref:System.Windows.Controls.DataGridLength.Auto%2A> или <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, столбцы будут увеличиваться до ширины их самого широкого отображаемого содержимого.  Во время прокрутки эти режимы изменения размеров приводят к тому, что при прокрутке для отображения содержимого, размер которого больше текущего размера столбца, столбцы разворачиваются.  После того как содержимое будет прокручено из области видимости, столбцы не уменьшаются.  
  
 Можно установить автоматическое изменение размеров столбцов <xref:System.Windows.Controls.DataGrid> в пределах указанных границ или задать для столбцов фиксированные размеры.  В следующей таблице приведены свойства, которые можно задавать для управления размерами столбцов.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>|Задает верхнюю границу для всех столбцов <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=fullName>|Задает верхнюю границу для отдельного столбца.  Переопределяет свойство <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>|Задает нижнюю границу для всех столбцов <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=fullName>|Задает нижнюю границу для отдельного столбца.  Переопределяет свойство <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>|Задает определенную ширину всех столбцов <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName>|Задает фиксированную ширину отдельного столбца.  Переопределяет свойство <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>.|  
  
### Заголовки столбцов DataGrid  
 По умолчанию заголовки столбцов <xref:System.Windows.Controls.DataGrid> отображаются.  Для скрытия заголовков столбцов нужно установить для свойства <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> значение <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> или <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>.  По умолчанию при отображении заголовков столбцов они автоматически меняют размер в соответствии с содержимым.  Можно установить фиксированную высоту заголовков столбцов, задав значение свойства <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=fullName>.  
  
### Изменение размеров с помощью мыши  
 Пользователи могут изменять размеры столбцов <xref:System.Windows.Controls.DataGrid>, перетаскивая разделители заголовков строк или столбцов.  Элемент управления <xref:System.Windows.Controls.DataGrid> также поддерживает автоматическое изменение размеров строк и столбцов путем двойного щелчка разделителя заголовка строки или столбца.  Можно запретить изменение размеров определенных столбцов, задав свойству <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> значение `false` для отдельных столбцов.  Чтобы запретить пользователям изменять размеры всех столбцов, задайте свойству <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> значение `false`.  Чтобы запретить пользователям изменять размеры всех строк, задайте свойству <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=fullName> значение `false`.  
  
## См. также  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGridColumn>   
 <xref:System.Windows.Controls.DataGridLength>   
 <xref:System.Windows.Controls.DataGridLengthConverter>