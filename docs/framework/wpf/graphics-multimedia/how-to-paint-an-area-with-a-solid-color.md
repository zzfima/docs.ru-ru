---
title: Практическое руководство. Закраска области сплошным цветом
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849526"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Практическое руководство. Закраска области сплошным цветом
Чтобы нарисовать область с твердым цветом, вы можете <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>использовать предопределенные системные кисти, такие как или , или вы можете создать новый <xref:System.Windows.Media.SolidColorBrush> и описать его <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью альфа, красный, зеленый и синий значения. В XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.  
  
 Следующие примеры используют каждый <xref:System.Windows.Shapes.Rectangle> из этих методов, чтобы покрасить синий.  
  
## <a name="example"></a>Пример  
 **Использование стандартной кисти**  
  
 В следующем примере используется <xref:System.Windows.Media.Brushes.Blue%2A> предопределенная кисть для рисования прямоугольника синего цвета.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Использование шестнадцатеричной нотации**  
  
 В следующем примере используется шестнадцатеричная нотация из 8 цифр для закрашивания прямоугольника синим цветом.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Использование значений ARGB**  
  
 Следующий пример <xref:System.Windows.Media.SolidColorBrush> создает и <xref:System.Windows.Media.SolidColorBrush.Color%2A> описывает его использование значений ARGB для синего цвета.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Для других способов описания <xref:System.Windows.Media.Color> цвета, увидеть структуру.  
  
 **Похожие темы**  
  
 Для получения <xref:System.Windows.Media.SolidColorBrush> дополнительной информации и дополнительных примеров смотрите обзор [обзора картины с твердыми цветами и градиентами.](painting-with-solid-colors-and-gradients-overview.md)  
  
 Этот пример кода является частью более <xref:System.Windows.Media.SolidColorBrush> крупного примера, предусмотренного для класса. Для полного образца [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)см.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Brushes>
