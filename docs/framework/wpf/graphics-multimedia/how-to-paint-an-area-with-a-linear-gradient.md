---
title: "Как закрасить область с линейным градиентом | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "кисти, рисование с линейным градиентом"
  - "линейные градиенты, рисование с помощью"
  - "рисование, с линейным градиентом"
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Как закрасить область с линейным градиентом
В этом примере показано использование класса <xref:System.Windows.Media.LinearGradientBrush> для закрашивания области с линейным градиентом.  В следующем примере, <xref:System.Windows.Shapes.Shape.Fill%2A> для <xref:System.Windows.Shapes.Rectangle> закрашено с использованием диагонального линейного градиента с переходом цвета от желтого к красному, синему и затем зеленому.  
  
## Пример  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Диагональный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.png "graphicsmm\_DiagonalLGB")  
  
 Для создания горизонтального линейного градиента следует изменить значения <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> класса <xref:System.Windows.Media.LinearGradientBrush> на \(0,0.5\) и \(1,0.5\).  В следующем примере объект <xref:System.Windows.Shapes.Rectangle> окрашивается с помощью горизонтального линейного градиента.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Горизонтальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.png "graphicsmm\_HorizontalLGB")  
  
 Для создания вертикального линейного градиента следует изменить значения <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> класса <xref:System.Windows.Media.LinearGradientBrush> на \(0.5,0\) и \(0.5,1\).  В следующем примере объект <xref:System.Windows.Shapes.Rectangle> окрашивается с помощью вертикального линейного градиента.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  
  
 ![Вертикальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.png "graphicsmm\_VerticalLGB")  
  
> [!NOTE]
>  В примерах в этом разделе используется система координат по умолчанию для установки начальной и конечной точки.  Система координат по умолчанию связана с ограничивающим прямоугольником: 0 указывает 0 процентов ограничивающего прямоугольника и 1 — 100 процентов.  Можно изменить эту систему координат, задав свойству <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode?displayProperty=fullName>.  Абсолютная система координат определяется не относительно ограничивающего прямоугольника.  Значения интерпретируются непосредственно в локальной области.  
  
 Дополнительные примеры см. в разделе [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) \("Примеры использования кистей"\).  Дополнительные сведения о градиенте и других типах кистей см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).