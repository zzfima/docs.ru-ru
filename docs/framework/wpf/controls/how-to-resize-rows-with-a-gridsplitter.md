---
title: Как выполнить Изменение размера строк с помощью разделителя GridSplitter
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 93a04ce55a10f54a6770c279f1773491d7aa463f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740142"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Как выполнить Изменение размера строк с помощью разделителя GridSplitter
В этом примере показано, как использовать горизонтальный <xref:System.Windows.Controls.GridSplitter> для перераспределения пространства между двумя строками в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Пример  
 **Создание GridSplitter, который накладывается на границы строки**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних строк в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Row%2A> вложенного свойства зависимостей для одной из строк, которые вы хотите изменить. Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте <xref:System.Windows.Controls.Grid.ColumnSpan%2A> вложенное свойство, чтобы указать число столбцов. Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> для <xref:System.Windows.VerticalAlignment.Top> или <xref:System.Windows.VerticalAlignment.Bottom> (указываемое выравнивание зависит от какой из двух строк вы хотите изменить). Наконец, установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 В следующем примере показано, как определить горизонтальный <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних строк.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Объект <xref:System.Windows.Controls.GridSplitter> , не имеющий собственной строки может быть скрыт другими элементами управления в <xref:System.Windows.Controls.Grid>. Дополнительные сведения о том, как предотвратить возникновение этой проблемы, см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Создание GridSplitter, который занимает строку**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , который занимает строку в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Row%2A> вложенного свойства зависимостей для одной из строк, которые вы хотите изменить. Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте <xref:System.Windows.Controls.Grid.ColumnSpan%2A> присоединенное свойство число столбцов. Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> для <xref:System.Windows.VerticalAlignment.Center>, задайте <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Stretch>и задайте <xref:System.Windows.Controls.RowDefinition.Height%2A> из строки, содержащей <xref:System.Windows.Controls.GridSplitter> для <xref:System.Windows.GridLength.Auto%2A>.  
  
 В следующем примере показано, как определить горизонтальный <xref:System.Windows.Controls.GridSplitter> который занимает строку и изменяет размеры строк на обеих сторонах.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.GridSplitter>
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
