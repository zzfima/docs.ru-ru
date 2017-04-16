---
title: "Практическое руководство. Закраска области сплошным цветом | Microsoft Docs"
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
  - "кисти, закраска сплошным цветом"
  - "рисование, сплошным цветом"
  - "сплошной цвет, рисование с помощью"
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Закраска области сплошным цветом
Для закраски области сплошным цветом можно использовать стандартную системную кисть, например <xref:System.Windows.Media.Brushes.Red%2A> или <xref:System.Windows.Media.Brushes.Blue%2A>, или же можно создать новую <xref:System.Windows.Media.SolidColorBrush> и описать ее <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью значений «альфа», «красный», «зеленый» и «синий».  В языке XAML можно также закрасить область сплошным цветом, используя шестнадцатеричную нотацию.  
  
 В следующих примерах из этих методов используется для рисования синего <xref:System.Windows.Shapes.Rectangle>.  
  
## Пример  
 **Использование стандартной кисти**  
  
 В следующем примере используется стандартная кисть <xref:System.Windows.Media.Brushes.Blue%2A> для рисования синего прямоугольника.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Использование шестнадцатеричной нотации**  
  
 В следующем примере используется 8 цифр шестнадцатеричного формата для рисования синего прямоугольника.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Использование значений ARGB**  
  
 В следующем примере создается <xref:System.Windows.Media.SolidColorBrush> и задается ее <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью значений ARGB для получения синего цвета.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Другие способы задания цвета см. в описании структуры <xref:System.Windows.Media.Color>.  
  
 **Связанные разделы**  
  
 Дополнительные сведения о <xref:System.Windows.Media.SolidColorBrush> и дополнительные примеры содержатся в обзоре [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
 Данный пример кода является частью большого примера, приведенного в описании класса <xref:System.Windows.Media.SolidColorBrush>.  Полный код примера см. на веб\-странице [Пример Brushes](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## См. также  
 <xref:System.Windows.Media.Brushes>