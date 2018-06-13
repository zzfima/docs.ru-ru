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
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="3f0f2-102">Практическое руководство. Повышение производительности отрисовки за счет кэширования элемента</span><span class="sxs-lookup"><span data-stu-id="3f0f2-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="3f0f2-103">Используйте <xref:System.Windows.Media.BitmapCache> класса для повышения производительности отрисовки сложных <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="3f0f2-104">Чтобы кэшировать элемент, необходимо создать новый экземпляр <xref:System.Windows.Media.BitmapCache> класса и назначьте его на элемент <xref:System.Windows.UIElement.CacheMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="3f0f2-105">Можно повторно использовать <xref:System.Windows.Media.BitmapCache> эффективно в <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f0f2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3f0f2-106">Example</span></span>  
 <span data-ttu-id="3f0f2-107">В следующем примере кода показано, как создать составной элемент и кэшировать его как растровое изображение, что улучшает производительность при анимации элемента.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="3f0f2-108">Элемент представляет собой полотно, содержащее геометрические фигуры с большим числом вершин.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="3f0f2-109">Объект <xref:System.Windows.Media.BitmapCache> по умолчанию назначается значения <xref:System.Windows.UIElement.CacheMode%2A> холста, и анимация демонстрирует гладкое масштабирование кэшированного растрового изображения.</span><span class="sxs-lookup"><span data-stu-id="3f0f2-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="3f0f2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3f0f2-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="3f0f2-111">Практическое руководство. Использование кэшированного элемента в качестве кисти</span><span class="sxs-lookup"><span data-stu-id="3f0f2-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
