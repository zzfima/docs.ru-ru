---
title: Практическое руководство. Заливка области с помощью линейного градиента
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916165"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Практическое руководство. Заливка области с помощью линейного градиента
В этом примере показано, как использовать <xref:System.Windows.Media.LinearGradientBrush> класс для закрашивания области с линейным градиентом. В следующем примере объект <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> для закрашивается с помощью диагонального линейного градиента, который переходит от желтого к красному к темному зеленому.  
  
## <a name="example"></a>Пример  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 На следующем рисунке показан градиент, созданный в предыдущем примере.  
  
 ![Диагональный линейный градиент](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Чтобы создать горизонтальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> в (0, 0,5) и (1, 0,5). В следующем примере объект <xref:System.Windows.Shapes.Rectangle> рисуется с горизонтальным линейным градиентом.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 На следующем рисунке показан градиент, созданный в предыдущем примере.  
  
 ![Горизонтальный линейный градиент](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Чтобы создать Вертикальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> значение <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush> для на (0,5, 0) и (0,5, 1). В следующем примере объект <xref:System.Windows.Shapes.Rectangle> рисуется с помощью вертикального линейного градиента.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 На следующем рисунке показан градиент, созданный в предыдущем примере.  
  
 ![Вертикальный линейный градиент](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
> В примерах этого раздела используется система координат по умолчанию для установки начальных и конечных точек. Система координат по умолчанию относится к ограничивающему прямоугольнику: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 указывает 100 процентов ограничивающего прямоугольника. Вы можете изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> для свойства значение. <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType> Абсолютная система координат не привязана к ограничивающему прямоугольнику. Значения интерпретируются непосредственно в локальной области.  
  
 Дополнительные примеры см. в разделе [образец кистей](https://go.microsoft.com/fwlink/?LinkID=159973). Дополнительные сведения о градиентах и других типах кистей см. [в статье Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).
