---
title: Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: b4652c06cfe6f048f6c75a11b9447d70d6820e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556154"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter
В этом примере показано, как создать вертикальной <xref:System.Windows.Controls.GridSplitter> для увеличения пространства между двумя столбцами в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Пример  
 **Создание GridSplitter, который накладывается на границы столбца**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних столбцов в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Column%2A> подключен к одному из столбцов, которые вы хотите изменить свойство. Если вашей <xref:System.Windows.Controls.Grid> имеет более одной строки, задайте <xref:System.Windows.Controls.Grid.RowSpan%2A> вложенное свойство числом строк. Затем установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Left> или <xref:System.Windows.HorizontalAlignment.Right> (выравнивание, которое можно задать зависит от двух столбцы, которого необходимо изменить). Задайте <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Объект <xref:System.Windows.Controls.GridSplitter> , не имеет свой собственный столбца может быть скрыт других элементов управления в <xref:System.Windows.Controls.Grid>. Дополнительные сведения о том, как предотвратить возникновение этой проблемы, см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Создание GridSplitter, который занимает столбец**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , занимает столбец в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Column%2A> подключен к одному из столбцов, которые вы хотите изменить свойство. Если ваш сетка имеет более одной строки, задайте <xref:System.Windows.Controls.Grid.RowSpan%2A> вложенное свойство числом строк. Затем установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> для <xref:System.Windows.HorizontalAlignment.Center>, задайте <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.VerticalAlignment.Stretch>и задайте <xref:System.Windows.Controls.ColumnDefinition.Width%2A> столбца, который содержит <xref:System.Windows.Controls.GridSplitter> для <xref:System.Windows.GridLength.Auto%2A>.  
  
 В следующем примере показан способ определения вертикальной <xref:System.Windows.Controls.GridSplitter> , занимает столбец и изменяет размеры столбцов на обеих сторонах.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridSplitter>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
