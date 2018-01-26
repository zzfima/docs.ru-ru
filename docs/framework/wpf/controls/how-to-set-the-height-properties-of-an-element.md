---
title: "Практическое руководство. Установка свойств высоты элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc06eea281f7761abfae74edf1547fc914b5655a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Практическое руководство. Установка свойств высоты элемента
## <a name="example"></a>Пример  
 В этом примере визуально показаны различия в поведении между четырьмя свойствами, связанных с высотой в отрисовки [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 <xref:System.Windows.FrameworkElement> Класс предоставляет четыре свойства, описывающие характеристики высоту элемента. Эти четыре свойства могут конфликтовать, и при этом, значение, которое имеет больший приоритет, определяется следующим образом: <xref:System.Windows.FrameworkElement.MinHeight%2A> значение имеет приоритет над <xref:System.Windows.FrameworkElement.MaxHeight%2A> значение, которое в свою очередь имеет приоритет над <xref:System.Windows.FrameworkElement.Height%2A> значение. Четвертое свойство <xref:System.Windows.FrameworkElement.ActualHeight%2A>, доступной только для чтения и сообщает о фактической высоте, определенной при взаимодействии с процессом макета.  
  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) как дочерний <xref:System.Windows.Controls.Canvas>. Можно изменить свойства высоты <xref:System.Windows.Shapes.Rectangle> с помощью ряда <xref:System.Windows.Controls.ListBox> элементы, представляющие значения свойств <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, и <xref:System.Windows.FrameworkElement.Height%2A>. Таким образом визуально отображается приоритет каждого свойства.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода обработки событий, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> вызывает событие. Каждый обработчик принимает входные данные <xref:System.Windows.Controls.ListBox>, анализирует его как <xref:System.Double>и применяет значение к указанному свойству высоты. Значения высоты также преобразуются в строку и записываются в различные <xref:System.Windows.Controls.TextBlock> элементы (определение этих элементов не представлено в выбранном XAML).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Полный пример см. в разделе [свойства высоты-пример](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [Определение свойств ширины элемента](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Пример свойств высоты](http://go.microsoft.com/fwlink/?LinkID=159993)
