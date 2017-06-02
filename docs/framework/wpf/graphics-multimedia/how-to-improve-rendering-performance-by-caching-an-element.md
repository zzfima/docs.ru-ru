---
title: "Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента | Microsoft Docs"
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
  - "BitmapCache [WPF], увеличение производительности отрисовки"
  - "CacheMode [WPF], увеличение производительности отрисовки"
  - "производительность [WPF], кэширование элемента"
  - "производительность отрисовки [WPF], кэширование элемента"
  - "UIElement [WPF], кэширование"
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента
Класс <xref:System.Windows.Media.BitmapCache> используется для повышения производительности отрисовки сложных элементов <xref:System.Windows.UIElement>.  Для кэширования элемента создайте новый экземпляр класса <xref:System.Windows.Media.BitmapCache> и задайте его в свойстве <xref:System.Windows.UIElement.CacheMode%2A> элемента.  Объект <xref:System.Windows.Media.BitmapCache> поддерживает эффективное многократное использование в объекте <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## Пример  
 В следующем примере кода показано создание сложного элемента и кэширование его в виде растрового рисунка. Кэширование повышает производительность анимации элемента.  Элемент представляет собой полотно, содержащее геометрические фигуры с большим числом вершин.  В свойстве <xref:System.Windows.UIElement.CacheMode%2A> полотна задается объект <xref:System.Windows.Media.BitmapCache> со значениями по умолчанию, и анимация демонстрирует гладкое масштабирование кэшированного растрового изображения.  
  
 [!code-xml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## См. также  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Практическое руководство. Использование кэшированного элемента в качестве кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)