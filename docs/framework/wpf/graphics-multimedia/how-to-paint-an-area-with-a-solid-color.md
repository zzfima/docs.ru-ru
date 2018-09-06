---
title: Практическое руководство. Закраска области сплошным цветом
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 017c685139979ec3aa411be6e6b5fdf0e91657de
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878448"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Практическое руководство. Закраска области сплошным цветом
Чтобы закрасить область сплошным цветом, можно использовать стандартную системную кисть, например <xref:System.Windows.Media.Brushes.Red%2A> или <xref:System.Windows.Media.Brushes.Blue%2A>, или создать новый <xref:System.Windows.Media.SolidColorBrush> и описать его <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью значений альфа, красного, зеленого и синего. В XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.  
  
 В следующих примерах используется каждый из этих приемов для закрашивания <xref:System.Windows.Shapes.Rectangle> синий.  
  
## <a name="example"></a>Пример  
 **Использование стандартной кисти**  
  
 В следующем примере используется стандартная кисть <xref:System.Windows.Media.Brushes.Blue%2A> для закрашивания прямоугольника синим цветом.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Использование шестнадцатеричной нотации**  
  
 В следующем примере используется шестнадцатеричная нотация из 8 цифр для закрашивания прямоугольника синим цветом.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Использование значений ARGB**  
  
 В следующем примере создается <xref:System.Windows.Media.SolidColorBrush> и описывает его <xref:System.Windows.Media.SolidColorBrush.Color%2A> использование ARGB значений для получения синего цвета.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Другие способы описания цвета см. в разделе <xref:System.Windows.Media.Color> структуры.  
  
 **См. также**  
  
 Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> и Дополнительные примеры см. в разделе [закраске сплошным цветом и градиентом Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Обзор.  
  
 Данный пример кода является частью большего примера для <xref:System.Windows.Media.SolidColorBrush> класса. Полный пример см. в разделе [Пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Brushes>
