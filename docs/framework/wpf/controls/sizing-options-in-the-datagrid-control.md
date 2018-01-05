---
title: "Параметры изменения размеров элемента управления DataGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4219dc88a263b73aa89812a2f841a920c804796b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sizing-options-in-the-datagrid-control"></a>Параметры изменения размеров элемента управления DataGrid
Различные параметры, доступные для управления как <xref:System.Windows.Controls.DataGrid> изменяет свой размер. <xref:System.Windows.Controls.DataGrid>И отдельных строк и столбцов в <xref:System.Windows.Controls.DataGrid>, можно задать размер автоматически в соответствии с содержимым, или могут быть присвоены определенные значения. По умолчанию <xref:System.Windows.Controls.DataGrid> будет увеличиваться или уменьшаться в соответствии с размером его содержимого.  
  
## <a name="sizing-the-datagrid"></a>Изменение размера DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Меры предосторожности при использовании автоматического изменения размера  
 По умолчанию <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства <xref:System.Windows.Controls.DataGrid> присвоено <xref:System.Double.NaN?displayProperty=nameWithType> («`Auto`» в XAML) и <xref:System.Windows.Controls.DataGrid> будет изменение размера по его содержимое.  
  
 При размещении внутри контейнера, не ограничивает размер своих дочерних элементов, таких как <xref:System.Windows.Controls.Canvas> или <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.DataGrid> расширяется за пределы видимых границ контейнера и не будет отображаться полосы прокрутки. Эта проблема влияет на удобство использования и производительности.  
  
 При привязке к набору данных, если <xref:System.Windows.FrameworkElement.Height%2A> из <xref:System.Windows.Controls.DataGrid> — не ограничено, она будет продолжать добавьте строку для каждого элемента данных в привязанном наборе. Это может привести к <xref:System.Windows.Controls.DataGrid> рост за границами видимой приложения, которые добавляются строки. <xref:System.Windows.Controls.DataGrid> Не будет отображать полосы прокрутки в этом случае из-за его <xref:System.Windows.FrameworkElement.Height%2A> будет продолжать увеличиваться для размещения новых строк.  
  
 Объект создается для каждой строки в <xref:System.Windows.Controls.DataGrid>. Если вы работаете с большим набором данных и разрешить <xref:System.Windows.Controls.DataGrid> автоматическое изменение размера, создание большого числа объектов может повлиять на производительность приложения.  
  
 Чтобы избежать этих проблем при работе с большими наборами данных, рекомендуется специально настроены <xref:System.Windows.FrameworkElement.Height%2A> из <xref:System.Windows.Controls.DataGrid> или поместить его в контейнер, который ограничит его <xref:System.Windows.FrameworkElement.Height%2A>, такие как <xref:System.Windows.Controls.Grid>. Когда <xref:System.Windows.FrameworkElement.Height%2A> ограничен, <xref:System.Windows.Controls.DataGrid> создает только строк, которые могут уместиться в пределах указанного <xref:System.Windows.FrameworkElement.Height%2A>и будет повторно использовать эти строки для отображения новых данных.  
  
### <a name="setting-the-datagrid-size"></a>Задание размера DataGrid  
 <xref:System.Windows.Controls.DataGrid> Можно задать автоматическое изменение размеров в пределах указанных границ или <xref:System.Windows.Controls.DataGrid> можно присвоить значение определенного размера. В следующей таблице показаны свойства, которые могут быть установлены для элемента управления <xref:System.Windows.Controls.DataGrid> размер.  
  
|Свойство.|Описание:|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Задает высоту для <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Задает верхнюю границу высоты <xref:System.Windows.Controls.DataGrid>. <xref:System.Windows.Controls.DataGrid> Будет увеличиваться по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Задает нижнюю границу высоты <xref:System.Windows.Controls.DataGrid>. <xref:System.Windows.Controls.DataGrid> Уменьшить по вертикали до достижения этой высоты.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Задает ширину для <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Задает верхнюю границу ширины <xref:System.Windows.Controls.DataGrid>. <xref:System.Windows.Controls.DataGrid> Увеличивается по горизонтали до достижения этой ширины.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Задает ширину нижней границы <xref:System.Windows.Controls.DataGrid>. <xref:System.Windows.Controls.DataGrid> Уменьшается по горизонтали до достижения этой ширины.|  
  
## <a name="sizing-rows-and-row-headers"></a>Изменение размеров строк и заголовки строк  
  
### <a name="datagrid-rows"></a>Строк DataGrid  
 По умолчанию <xref:System.Windows.Controls.DataGrid> строки <xref:System.Windows.FrameworkElement.Height%2A> свойству <xref:System.Double.NaN?displayProperty=nameWithType> («`Auto`» в языке XAML), высота строки будет увеличиваться до размера, его содержимое. Высоту всех строк в <xref:System.Windows.Controls.DataGrid> можно указать, задав <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> свойство. Пользователи могут изменять высоту строк путем перетаскивания разделителей строк заголовка.  
  
### <a name="datagrid-row-headers"></a>Заголовки строк DataGrid  
 Отображение заголовков строк <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> свойству необходимо присвоить значение <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> или <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. По умолчанию отображаются заголовки строк и их размер автоматически изменяется в соответствии с содержимым. Заголовки строк можно фиксированную ширину, задав <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> свойство.  
  
## <a name="sizing-columns-and-column-headers"></a>Изменение размеров столбцов и заголовков столбцов  
  
### <a name="datagrid-columns"></a>Столбцы DataGrid  
 <xref:System.Windows.Controls.DataGrid> Использует значения <xref:System.Windows.Controls.DataGridLength> и <xref:System.Windows.Controls.DataGridLengthUnitType> структура для указания режима абсолютного или автоматического изменения размеров.  
  
 В следующей таблице показаны значения, предоставленные <xref:System.Windows.Controls.DataGridLengthUnitType> структуры.  
  
|name|Описание:|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Значение по умолчанию автоматического изменения размеров размеры режим <xref:System.Windows.Controls.DataGrid> столбцы на основе содержимого ячеек и заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Автоматическое основе ячеек размеры режим изменения размера <xref:System.Windows.Controls.DataGrid> столбцы на основе содержимого ячеек в столбце, за исключением заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Автоматически на основе заголовка размеры режим изменения размера <xref:System.Windows.Controls.DataGrid> столбцы на основе содержимого заголовков столбцов.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Точечных размеры режим изменения размера <xref:System.Windows.Controls.DataGrid> столбцов на основании числовых значений, содержащихся.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|Режим изменения размера типа «звезда» используется для распределения доступного места взвешенной пропорции.<br /><br /> В языке XAML звезда выражается n *, где n представляет числовое значение. 1\* эквивалентно \*. Например, если два столбцов в <xref:System.Windows.Controls.DataGrid> имеют ширину \* и 2\*, первый столбец получит одну часть доступного пространства, а второй столбец получит две части доступного пространства.|  
  
 <xref:System.Windows.Controls.DataGridLengthConverter> Класс может использоваться для преобразования данных между числовыми или строковыми значениями и <xref:System.Windows.Controls.DataGridLength> значения.  
  
 По умолчанию <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> свойству <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>и <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> свойству <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Если значение режим изменения размера <xref:System.Windows.Controls.DataGridLength.Auto%2A> или <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, столбцы будут увеличиваться до ширины их самого широкого отображаемого содержимого. Во время прокрутки эти режимы изменения размеров приводят столбцы для отображения содержимого, размер которого больше текущего размера столбца в области просмотра. Столбец не будет сокращен после содержимого находится вне области просмотра.  
  
 Столбцы в <xref:System.Windows.Controls.DataGrid> также можно задать автоматическое изменение размеров только в пределах указанных границ или столбцы, которые можно задать для определенного размера. Ниже приведены свойства, которые могут быть установлены для управления размеры столбцов.  
  
|Свойство.|Описание:|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Задает верхнюю границу для всех столбцов в <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Задает верхнюю границу для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Задает нижнюю границу для всех столбцов в <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Задает нижнюю границу для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Задает ширину для всех столбцов в <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Задает ширину для отдельного столбца. Переопределяет <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Заголовки столбцов DataGrid  
 По умолчанию <xref:System.Windows.Controls.DataGrid> отображаются заголовки столбцов. Чтобы скрыть заголовки столбцов <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> свойству необходимо присвоить значение <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> или <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. По умолчанию при отображении заголовков столбцов, они автоматически меняют размер в соответствии с содержимым. Может быть фиксированную высоту заголовков столбцов, задав <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> свойство.  
  
### <a name="resizing-with-the-mouse"></a>Изменение размеров с помощью мыши  
 Пользователь может изменять размер <xref:System.Windows.Controls.DataGrid> строк и столбцов, перетаскивая разделители заголовков строк или столбцов. <xref:System.Windows.Controls.DataGrid> Также поддерживает автоматическое изменение размеров строк и столбцов, дважды щелкнув разделитель заголовка строки или столбца. Чтобы предотвратить изменение размеров определенных столбцов, задайте <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> свойства `false` для отдельных столбцов. Чтобы запретить пользователям изменять размеры всех столбцов, задайте <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> свойства `false`. Чтобы запретить пользователям изменять размеры всех строк, задайте <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> свойства `false`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGridColumn>  
 <xref:System.Windows.Controls.DataGridLength>  
 <xref:System.Windows.Controls.DataGridLengthConverter>
