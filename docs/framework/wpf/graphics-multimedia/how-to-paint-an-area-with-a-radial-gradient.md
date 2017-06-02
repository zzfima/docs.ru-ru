---
title: "Практическое руководство. Закраска области с применением радиального градиента | Microsoft Docs"
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
  - "кисти, закрашивание с радиальным градиентом"
  - "рисование, с радиальным градиентом"
  - "радиальные градиенты, рисование с помощью"
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Закраска области с применением радиального градиента
В этом примере показано использование класса <xref:System.Windows.Media.RadialGradientBrush> для закраски области с применением радиального градиента.  
  
## Пример  
 В следующем примере класс <xref:System.Windows.Media.RadialGradientBrush> используется для закраски прямоугольника с применением радиального градиента, изменяющегося от желтого до красного, синего и зеленого.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 На следующем рисунке показан градиент из предыдущего примера.  Ограничения градиента выделены.  
  
 ![Остановки градиента в радиусном градиенте](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
> [!NOTE]
>  В примерах этого раздела для задания контрольных точек используется система координат по умолчанию.  Система координат по умолчанию связана с ограничивающим прямоугольником: 0 указывает 0 процентов ограничивающего прямоугольника и 1 — 100 процентов.  Можно изменить эту систему координат, задав свойству <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode>.  Абсолютная система координат определяется не относительно ограничивающего прямоугольника.  Значения интерпретируются непосредственно в локальной области.  
  
 Дополнительные примеры по <xref:System.Windows.Media.RadialGradientBrush> см. в разделе [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  Дополнительные сведения о градиенте и других типах кистей см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).