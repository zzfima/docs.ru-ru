---
title: Как выполнить Повышение производительности отрисовки за счет кэширования элемента
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 79f427198be370d9cb48cab429906202a62bb72d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647584"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="67d30-102">Как выполнить Повышение производительности отрисовки за счет кэширования элемента</span><span class="sxs-lookup"><span data-stu-id="67d30-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="67d30-103">Используйте <xref:System.Windows.Media.BitmapCache> класс повышать производительность отрисовки сложных <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="67d30-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="67d30-104">Для кэширования элемента, создайте новый экземпляр класса <xref:System.Windows.Media.BitmapCache> класса и его назначение этого элемента <xref:System.Windows.UIElement.CacheMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="67d30-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="67d30-105">Вы можете повторно использовать <xref:System.Windows.Media.BitmapCache> эффективно в <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="67d30-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d30-106">Пример</span><span class="sxs-lookup"><span data-stu-id="67d30-106">Example</span></span>  
 <span data-ttu-id="67d30-107">В следующем примере кода показано, как создать составной элемент и кэшировать его как растровое изображение, что повышает производительность, когда элемент анимируется.</span><span class="sxs-lookup"><span data-stu-id="67d30-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="67d30-108">Элемент представляет собой полотно, содержащее геометрические фигуры с большим числом вершин.</span><span class="sxs-lookup"><span data-stu-id="67d30-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="67d30-109">Объект <xref:System.Windows.Media.BitmapCache> имеет значения по умолчанию назначено значений <xref:System.Windows.UIElement.CacheMode%2A> Canvas, и анимация демонстрирует гладкое масштабирование кэшированного растрового изображения.</span><span class="sxs-lookup"><span data-stu-id="67d30-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="67d30-110">См. также</span><span class="sxs-lookup"><span data-stu-id="67d30-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="67d30-111">Практическое руководство. Использование кэшированного элемента в качестве кисти</span><span class="sxs-lookup"><span data-stu-id="67d30-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
