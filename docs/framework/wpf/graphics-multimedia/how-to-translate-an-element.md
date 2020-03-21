---
title: Практическое руководство. Смещение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111976"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="4a17b-102">Практическое руководство. Смещение элемента</span><span class="sxs-lookup"><span data-stu-id="4a17b-102">How to: Translate an Element</span></span>
<span data-ttu-id="4a17b-103">В этом примере показано, как переводить <xref:System.Windows.Media.TranslateTransform>(двигать) элемент с помощью .</span><span class="sxs-lookup"><span data-stu-id="4a17b-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="4a17b-104">Класс <xref:System.Windows.Media.TranslateTransform> особенно полезен для движущихся элементов внутри панелей, которые не поддерживают абсолютное позиционирование.</span><span class="sxs-lookup"><span data-stu-id="4a17b-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="4a17b-105">Например, применяя <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента, можно переместить элемент <xref:System.Windows.Controls.StackPanel> в <xref:System.Windows.Controls.DockPanel>пределах или .</span><span class="sxs-lookup"><span data-stu-id="4a17b-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="4a17b-106">Используйте <xref:System.Windows.Media.TranslateTransform.X%2A> свойство, <xref:System.Windows.Media.TranslateTransform> чтобы указать количество, в пикселях, чтобы переместить элемент вдоль оси x.</span><span class="sxs-lookup"><span data-stu-id="4a17b-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="4a17b-107">Используйте <xref:System.Windows.Media.TranslateTransform.Y%2A> свойство, чтобы указать количество в пикселях, чтобы переместить элемент вдоль y-оси.</span><span class="sxs-lookup"><span data-stu-id="4a17b-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="4a17b-108">Наконец, <xref:System.Windows.Media.TranslateTransform> примените свойство <xref:System.Windows.UIElement.RenderTransform%2A> элемента.</span><span class="sxs-lookup"><span data-stu-id="4a17b-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="4a17b-109">В следующем примере используется для перемещения элемента <xref:System.Windows.Media.TranslateTransform> 50 пикселей вправо и 50 пикселей вниз.</span><span class="sxs-lookup"><span data-stu-id="4a17b-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a17b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="4a17b-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="4a17b-111">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)</span><span class="sxs-lookup"><span data-stu-id="4a17b-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a17b-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a17b-112">See also</span></span>

- [<span data-ttu-id="4a17b-113">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="4a17b-113">Transforms Overview</span></span>](transforms-overview.md)
