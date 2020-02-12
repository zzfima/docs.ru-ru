---
title: Практическое руководство. Установка свойств ширины элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124277"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Практическое руководство. Установка свойств ширины элемента
## <a name="example"></a>Пример  
 В этом примере визуально отображаются различия в поведении отрисовки из четырех свойств, связанных с шириной, в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Класс <xref:System.Windows.FrameworkElement> предоставляет четыре свойства, описывающие характеристики ширины элемента. Эти четыре свойства могут конфликтовать, и, когда это происходит, значение, которое имеет приоритет, определяется следующим образом: значение <xref:System.Windows.FrameworkElement.MinWidth%2A> имеет приоритет над значением <xref:System.Windows.FrameworkElement.MaxWidth%2A>, которое, в свою очередь, имеет приоритет над значением <xref:System.Windows.FrameworkElement.Width%2A>. Четвертое свойство, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, доступно только для чтения и сообщает фактическую ширину, определенную взаимодействием с процессом макета.  
  
 В следующих [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах элемент <xref:System.Windows.Shapes.Rectangle> (`rect1`) рисуется в качестве дочернего элемента для <xref:System.Windows.Controls.Canvas>. Свойства ширины <xref:System.Windows.Shapes.Rectangle> можно изменить с помощью ряда элементов <xref:System.Windows.Controls.ListBox>, представляющих значения свойств <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>и <xref:System.Windows.FrameworkElement.Width%2A>. Таким образом, для каждого свойства отображается визуальный порядок.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода программной части обработаны события, которые вызывает событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Каждый пользовательский метод принимает входные данные из <xref:System.Windows.Controls.ListBox>, анализирует значение как <xref:System.Double>и применяет это значение к указанному свойству, связанному с шириной. Значения ширины также преобразуются в строку и записываются в различные элементы <xref:System.Windows.Controls.TextBlock> (определение этих элементов не отображается в выбранном коде XAML).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Полный пример см. в разделе [Пример сравнения свойств ширины](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Общие сведения о панелях](panels-overview.md)
- [Определение свойств высоты элемента](how-to-set-the-height-properties-of-an-element.md)
- [Сравнение свойств ширины — пример](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
