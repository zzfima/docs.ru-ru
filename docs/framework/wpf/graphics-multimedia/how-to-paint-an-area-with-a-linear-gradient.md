---
title: "Как закрасить область с линейным градиентом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eec4ec2fc7ba99081eaafa6803d20c99bebc6c2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Как закрасить область с линейным градиентом
В этом примере показано, как использовать <xref:System.Windows.Media.LinearGradientBrush> класса Закраска области с линейным градиентом. В следующем примере <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle> отрисовывается с диагонального линейного градиента, которая переходит с желтого на красный цвет на синий и зеленого.  
  
## <a name="example"></a>Пример  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Диагональный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Чтобы создать горизонтальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> из <xref:System.Windows.Media.LinearGradientBrush> для (0,0.5) и (1,0.5). В следующем примере <xref:System.Windows.Shapes.Rectangle> отрисовывается с горизонтального линейного градиента.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Горизонтальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Чтобы создать Вертикальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> из <xref:System.Windows.Media.LinearGradientBrush> на (0.5,0) и (0.5,1). В следующем примере <xref:System.Windows.Shapes.Rectangle> отрисовывается с помощью вертикального линейного градиента.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Вертикальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  В примерах в этом разделе используется система координат по умолчанию для установки начальной и конечной точек. Система координат по умолчанию задается относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 — 100 процентов ограничивающего прямоугольника. Можно изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Абсолютная система координат не привязана к ограничивающему прямоугольнику. Значения интерпретируются непосредственно в локальной области.  
  
 Дополнительные примеры см. в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973). Дополнительные сведения о градиенте и других типах кистей см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
