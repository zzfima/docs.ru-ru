---
title: "Практическое руководство. Смещение элемента | Microsoft Docs"
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
  - "классы, TranslateTransform"
  - "графика, переводы"
  - "TranslateTransform - класс"
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Смещение элемента
В этом примере рассмотрен способ преобразования \(перемещения\) элемента с помощью <xref:System.Windows.Media.TranslateTransform>.  
  
 Класс <xref:System.Windows.Media.TranslateTransform> особенно полезен для перемещения элементов внутри панелей, которые не поддерживают абсолютное позиционирование.  Например, применяя <xref:System.Windows.Media.TranslateTransform> к свойству <xref:System.Windows.UIElement.RenderTransform%2A> элемента, можно переместить элемент в пределах <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel>.  
  
 Свойство <xref:System.Windows.Media.TranslateTransform.X%2A> из <xref:System.Windows.Media.TranslateTransform> используется для того, чтобы задать интервал в [пикселях](GTMT) и переместить элемент вдоль оси x.  Свойство <xref:System.Windows.Media.TranslateTransform.Y%2A> используется для того, чтобы задать интервал в пикселях и переместить элемент вдоль оси y.  Наконец, <xref:System.Windows.Media.TranslateTransform> применяется к свойству элемента <xref:System.Windows.UIElement.RenderTransform%2A>.  
  
 В следующем примере используется <xref:System.Windows.Media.TranslateTransform> для перемещения элемента на 50 [пикселей](GTMT) направо и на 50 пикселей вниз.  
  
## Пример  
 [!code-xml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Полный пример см. на веб\-странице [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## См. также  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)