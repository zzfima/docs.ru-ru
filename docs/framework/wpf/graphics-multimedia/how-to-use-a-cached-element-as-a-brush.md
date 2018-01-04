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
ms.workload: dotnet
ms.openlocfilehash: f463c15855e267a4c246625a8d06e627852f48a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
