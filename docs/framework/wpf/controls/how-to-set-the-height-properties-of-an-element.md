---
title: Практическое руководство. Установка свойств высоты элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124290"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Практическое руководство. Установка свойств высоты элемента
## <a name="example"></a>Пример  
 В этом примере визуально отображаются различия в поведении отрисовки четырех свойств, связанных с высотой, в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Класс <xref:System.Windows.FrameworkElement> предоставляет четыре свойства, описывающие характеристики высоты элемента. Эти четыре свойства могут конфликтовать, и, когда это происходит, значение, которое имеет приоритет, определяется следующим образом: значение <xref:System.Windows.FrameworkElement.MinHeight%2A> имеет приоритет над значением <xref:System.Windows.FrameworkElement.MaxHeight%2A>, которое, в свою очередь, имеет приоритет над значением <xref:System.Windows.FrameworkElement.Height%2A>. Четвертое свойство, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, доступно только для чтения и сообщает фактическую высоту, определенную взаимодействием с процессом макета.  
  
 В следующих [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах элемент <xref:System.Windows.Shapes.Rectangle> (`rect1`) рисуется в качестве дочернего элемента для <xref:System.Windows.Controls.Canvas>. Свойства высоты <xref:System.Windows.Shapes.Rectangle> можно изменить с помощью ряда элементов <xref:System.Windows.Controls.ListBox>, представляющих значения свойств <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>и <xref:System.Windows.FrameworkElement.Height%2A>. Таким образом, для каждого свойства отображается визуальный порядок.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода программной части обработаны события, которые вызывает событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Каждый обработчик принимает входные данные из <xref:System.Windows.Controls.ListBox>, анализирует значение как <xref:System.Double>и применяет это значение к указанному свойству, связанному с высотой. Значения высоты также преобразуются в строку и записываются в различные элементы <xref:System.Windows.Controls.TextBlock> (определение этих элементов не отображается в выбранном коде XAML).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Полный пример см. в разделе [образец свойств Height](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Определение свойств ширины элемента](how-to-set-the-width-properties-of-an-element.md)
- [Общие сведения о панелях](panels-overview.md)
- [Пример свойств высоты](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
