---
title: "Практическое руководство. Изменение размера строк с помощью разделителя GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6621cc0048270b97c42ff4c4e646b0ddd9ca3477
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Практическое руководство. Изменение размера строк с помощью разделителя GridSplitter
В этом примере показано, как использовать горизонтальный <xref:System.Windows.Controls.GridSplitter> для распределения пространства между двумя строками в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Пример  
 **Создание GridSplitter, который накладывается на границы строки**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних строк в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Row%2A> присоединенного свойства для одной из строк, которые вы хотите изменить. Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте <xref:System.Windows.Controls.Grid.ColumnSpan%2A> присоединенное свойство, чтобы указать число столбцов. Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> для <xref:System.Windows.VerticalAlignment.Top> или <xref:System.Windows.VerticalAlignment.Bottom> (выравнивание, которое можно задать зависит от на две строки, для которого необходимо изменить). Задайте <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 В следующем примере показано определение горизонтального <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних строк.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Объект <xref:System.Windows.Controls.GridSplitter> , не содержит собственную строку может быть скрыт других элементов управления в <xref:System.Windows.Controls.Grid>. Дополнительные сведения о том, как предотвратить возникновение этой проблемы, см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Создание GridSplitter, который занимает строку**  
  
 Чтобы указать <xref:System.Windows.Controls.GridSplitter> , занимает строку в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Row%2A> присоединенного свойства для одной из строк, которые вы хотите изменить. Если ваш <xref:System.Windows.Controls.Grid> имеет более чем один столбец, задайте <xref:System.Windows.Controls.Grid.ColumnSpan%2A> вложенному свойству количество столбцов. Затем установите <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> для <xref:System.Windows.VerticalAlignment.Center>, задайте <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Stretch>и задайте <xref:System.Windows.Controls.RowDefinition.Height%2A> строки, которая содержит <xref:System.Windows.Controls.GridSplitter> для <xref:System.Windows.GridLength.Auto%2A>.  
  
 В следующем примере показано определение горизонтального <xref:System.Windows.Controls.GridSplitter> , занимает строку и изменяет размеры строк на обеих сторонах.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridSplitter>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
