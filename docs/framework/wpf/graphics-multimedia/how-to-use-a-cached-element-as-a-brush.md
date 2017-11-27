---
title: "Практическое руководство. Использование кэшированного элемента в качестве кисти"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d0f0c60e9df6a1ec816b1f9cf5769c93b382ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Практическое руководство. Использование кэшированного элемента в качестве кисти
Используйте <xref:System.Windows.Media.BitmapCacheBrush> класса для эффективного многократного использования кэшированного элемента. Чтобы кэшировать элемент, необходимо создать новый экземпляр <xref:System.Windows.Media.BitmapCache> класса и назначьте его на элемент <xref:System.Windows.UIElement.CacheMode%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как повторно использовать кэшированный элемент. Кэшируемый элемент представляет <xref:System.Windows.Controls.Image> элемент управления, отображающий большое изображение. <xref:System.Windows.Controls.Image> Управления кэшируется как растровое изображение с помощью <xref:System.Windows.Media.BitmapCache> класса и кэш используется повторно путем назначения их <xref:System.Windows.Media.BitmapCacheBrush>. Кисть фона двадцать пять кнопок назначенный для демонстрации эффективного многократного использования.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
