---
title: Практическое руководство. Создание сложной сетки
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-complex-grid"></a>Практическое руководство. Создание сложной сетки
В этом примере показано, как использовать <xref:System.Windows.Controls.Grid> для создания макета, который выглядит как календарь.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется восемь строк и восемь столбцов с помощью <xref:System.Windows.Controls.RowDefinition> и <xref:System.Windows.Controls.ColumnDefinition> классы. Она использует <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> вложенные свойства, вместе с <xref:System.Windows.Shapes.Rectangle> элементы, которые заполняют фон различных столбцов и строк. Такой подход возможен, поскольку может существовать более одного элемента в каждой ячейке <xref:System.Windows.Controls.Grid>, принципиальное различие между <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Documents.Table>.  
  
 В примере используется вертикальная градиентов <xref:System.Windows.Shapes.Shape.Fill%2A> столбцы и строки, чтобы улучшить визуальное представление и удобочитаемость календаря. Стиль <xref:System.Windows.Controls.TextBlock> элементы, которые представляют даты и дни недели. <xref:System.Windows.Controls.TextBlock> элементы абсолютно располагаются в пределах их ячеек с помощью <xref:System.Windows.FrameworkElement.Margin%2A> свойств и свойств выравнивания, определенные в стиле для приложения.  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)
