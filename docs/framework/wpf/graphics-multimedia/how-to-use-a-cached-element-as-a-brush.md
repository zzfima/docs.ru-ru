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
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="c4127-102">Практическое руководство. Использование кэшированного элемента в качестве кисти</span><span class="sxs-lookup"><span data-stu-id="c4127-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="c4127-103">Используйте <xref:System.Windows.Media.BitmapCacheBrush> класса для эффективного многократного использования кэшированного элемента.</span><span class="sxs-lookup"><span data-stu-id="c4127-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="c4127-104">Чтобы кэшировать элемент, необходимо создать новый экземпляр <xref:System.Windows.Media.BitmapCache> класса и назначьте его на элемент <xref:System.Windows.UIElement.CacheMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="c4127-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4127-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c4127-105">Example</span></span>  
 <span data-ttu-id="c4127-106">В следующем примере кода показано, как повторно использовать кэшированный элемент.</span><span class="sxs-lookup"><span data-stu-id="c4127-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="c4127-107">Кэшируемый элемент представляет <xref:System.Windows.Controls.Image> элемент управления, отображающий большое изображение.</span><span class="sxs-lookup"><span data-stu-id="c4127-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="c4127-108"><xref:System.Windows.Controls.Image> Управления кэшируется как растровое изображение с помощью <xref:System.Windows.Media.BitmapCache> класса и кэш используется повторно путем назначения их <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="c4127-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="c4127-109">Кисть фона двадцать пять кнопок назначенный для демонстрации эффективного многократного использования.</span><span class="sxs-lookup"><span data-stu-id="c4127-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="c4127-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c4127-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="c4127-111">Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента</span><span class="sxs-lookup"><span data-stu-id="c4127-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
