---
title: "Практическое руководство. Закраска области сплошным цветом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a5fe948c3cc6088f238f1f8f53c26c5f1fa5b2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Практическое руководство. Закраска области сплошным цветом
Для рисования область сплошным цветом, можно использовать стандартную системную кисть, например <xref:System.Windows.Media.Brushes.Red%2A> или <xref:System.Windows.Media.Brushes.Blue%2A>, или можно создать новую <xref:System.Windows.Media.SolidColorBrush> и описания его <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью значений альфа, красного, зеленого и синего. В XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.  
  
 В следующих примерах используется каждый из этих способов для закрашивания <xref:System.Windows.Shapes.Rectangle> синим.  
  
## <a name="example"></a>Пример  
 **Использование стандартной кисти**  
  
 В следующем примере используется стандартная кисть <xref:System.Windows.Media.Brushes.Blue%2A> для рисования синего прямоугольника.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Использование шестнадцатеричной нотации**  
  
 В следующем примере используется шестнадцатеричная нотация из 8 цифр для закрашивания прямоугольника синим цветом.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Использование значений ARGB**  
  
 В следующем примере создается <xref:System.Windows.Media.SolidColorBrush> и описывает его <xref:System.Windows.Media.SolidColorBrush.Color%2A> использование ARGB значений для синего цвета.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Другие способы задания цвета в разделе <xref:System.Windows.Media.Color> структуры.  
  
 **См. также**  
  
 Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> и Дополнительные примеры см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Обзор.  
  
 Данный пример кода является частью большего примера, приведенного для <xref:System.Windows.Media.SolidColorBrush> класса. Полный пример см. в разделе [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Brushes>
