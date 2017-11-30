---
title: "Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d754d0ed2f3951c39b3eaeae097589adf3510f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента
Используйте <xref:System.Windows.Media.BitmapCache> класса для повышения производительности отрисовки сложных <xref:System.Windows.UIElement>. Чтобы кэшировать элемент, необходимо создать новый экземпляр <xref:System.Windows.Media.BitmapCache> класса и назначьте его на элемент <xref:System.Windows.UIElement.CacheMode%2A> свойство. Можно повторно использовать <xref:System.Windows.Media.BitmapCache> эффективно в <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создать составной элемент и кэшировать его как растровое изображение, что улучшает производительность при анимации элемента. Элемент представляет собой полотно, содержащее геометрические фигуры с большим числом вершин. Объект <xref:System.Windows.Media.BitmapCache> по умолчанию назначается значения <xref:System.Windows.UIElement.CacheMode%2A> холста, и анимация демонстрирует гладкое масштабирование кэшированного растрового изображения.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Практическое руководство. Использование кэшированного элемента в качестве кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
