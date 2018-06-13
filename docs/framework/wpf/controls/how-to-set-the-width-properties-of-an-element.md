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
ms.openlocfilehash: 72617744a8b2565857d19a1c6ef41bf4211c89ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554845"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Практическое руководство. Установка свойств ширины элемента
## <a name="example"></a>Пример  
 В этом примере визуально показаны различия в поведении между четырьмя свойствами, связанными с шириной в отрисовки [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 <xref:System.Windows.FrameworkElement> Класс предоставляет четыре свойства, описывающих характеристики ширины элемента. Эти четыре свойства могут конфликтовать, и при этом, значение, которое имеет больший приоритет, определяется следующим образом: <xref:System.Windows.FrameworkElement.MinWidth%2A> значение имеет приоритет над <xref:System.Windows.FrameworkElement.MaxWidth%2A> значение, которое в свою очередь имеет приоритет над <xref:System.Windows.FrameworkElement.Width%2A> значение. Четвертое свойство <xref:System.Windows.FrameworkElement.ActualWidth%2A>, доступной только для чтения и сообщает о фактической ширине, определенной при взаимодействии с процессом макета.  
  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) как дочерний <xref:System.Windows.Controls.Canvas>. Можно изменить свойства ширины <xref:System.Windows.Shapes.Rectangle> с помощью ряда <xref:System.Windows.Controls.ListBox> элементы, представляющие значения свойств <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, и <xref:System.Windows.FrameworkElement.Width%2A>. Таким образом визуально отображается приоритет каждого свойства.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 В следующих примерах кода обработки событий, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> вызывает событие. Каждый пользовательский метод принимает входные данные <xref:System.Windows.Controls.ListBox>, анализирует его как <xref:System.Double>и применяет значение к указанному свойству ширины. Значения ширины также преобразуются в строку и записываются в различные <xref:System.Windows.Controls.TextBlock> элементы (определение этих элементов не представлено в выбранном XAML).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Полный пример см. в разделе [пример сравнения свойств ширины](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Определение свойств высоты элемента](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [Пример сравнения свойств ширины](http://go.microsoft.com/fwlink/?LinkID=160050)
