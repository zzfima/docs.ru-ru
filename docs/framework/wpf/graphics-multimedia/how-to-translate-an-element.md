---
title: Практическое руководство. Смещение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 0089f294c54662d1ea4929ec25c08464072cbdde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561947"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="07d0b-102">Практическое руководство. Смещение элемента</span><span class="sxs-lookup"><span data-stu-id="07d0b-102">How to: Translate an Element</span></span>
<span data-ttu-id="07d0b-103">В этом примере показано, как для переноса (перемещения) элемента с помощью <xref:System.Windows.Media.TranslateTransform>.</span><span class="sxs-lookup"><span data-stu-id="07d0b-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="07d0b-104"><xref:System.Windows.Media.TranslateTransform> Класс особенно полезен для перемещения элементов внутри панелей, которые не поддерживают абсолютное позиционирование.</span><span class="sxs-lookup"><span data-stu-id="07d0b-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="07d0b-105">Например, применяя <xref:System.Windows.Media.TranslateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства элемента, можно переместить элемент в пределах <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="07d0b-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="07d0b-106">Используйте <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> , чтобы задать интервал в пикселях для перемещения элемента по оси x.</span><span class="sxs-lookup"><span data-stu-id="07d0b-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="07d0b-107">Используйте <xref:System.Windows.Media.TranslateTransform.Y%2A> свойство, чтобы задать интервал в пикселях для перемещения элемента по оси y.</span><span class="sxs-lookup"><span data-stu-id="07d0b-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="07d0b-108">Наконец, примените <xref:System.Windows.Media.TranslateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="07d0b-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="07d0b-109">В следующем примере используется <xref:System.Windows.Media.TranslateTransform> для перемещения элемента на 50 пикселей вправо до 50 пикселей вниз.</span><span class="sxs-lookup"><span data-stu-id="07d0b-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07d0b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="07d0b-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="07d0b-111">Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="07d0b-111">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d0b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="07d0b-112">See Also</span></span>  
 [<span data-ttu-id="07d0b-113">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="07d0b-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
