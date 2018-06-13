---
title: Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559302"
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
