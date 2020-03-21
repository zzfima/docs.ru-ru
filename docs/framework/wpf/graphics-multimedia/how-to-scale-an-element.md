---
title: Практическое руководство. Масштабирование элемента
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112054"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="9f91e-102">Практическое руководство. Масштабирование элемента</span><span class="sxs-lookup"><span data-stu-id="9f91e-102">How to: Scale an Element</span></span>
<span data-ttu-id="9f91e-103">В этом примере <xref:System.Windows.Media.ScaleTransform> показано, как использовать элемент для масштабирования.</span><span class="sxs-lookup"><span data-stu-id="9f91e-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="9f91e-104">Используйте <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> и свойства для изобрагивания элемента по указанному фактору.</span><span class="sxs-lookup"><span data-stu-id="9f91e-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="9f91e-105">Например, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> значение 1,5 растягивает элемент до 150 процентов от его первоначальной ширины.</span><span class="sxs-lookup"><span data-stu-id="9f91e-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="9f91e-106">Значение <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 0,5 сжимает высоту элемента на 50 процентов.</span><span class="sxs-lookup"><span data-stu-id="9f91e-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="9f91e-107">Используйте <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> и свойства, чтобы указать точку, которая является центром операции масштаба.</span><span class="sxs-lookup"><span data-stu-id="9f91e-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="9f91e-108">По умолчанию <xref:System.Windows.Media.ScaleTransform> a центрируется в точке (0,0), что соответствует верхнему левому углу прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9f91e-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="9f91e-109">Это приводит к перемещению элемента, а также к тому, чтобы он казался больше, потому что при <xref:System.Windows.Media.Transform>применении, вы изменяете пространство координат, в котором находится объект.</span><span class="sxs-lookup"><span data-stu-id="9f91e-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="9f91e-110">В следующем примере используется удвоение <xref:System.Windows.Media.ScaleTransform> размера 50 <xref:System.Windows.Shapes.Rectangle>на 50 .</span><span class="sxs-lookup"><span data-stu-id="9f91e-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="9f91e-111">Имеет <xref:System.Windows.Media.ScaleTransform> значение 0 (по умолчанию) <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>для обоих и .</span><span class="sxs-lookup"><span data-stu-id="9f91e-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f91e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9f91e-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="9f91e-113">Как правило, <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> вы устанавливаете и к центру<xref:System.Windows.FrameworkElement.Width%2A>объекта, <xref:System.Windows.FrameworkElement.Height%2A>который масштабируется: ( /2, /2).</span><span class="sxs-lookup"><span data-stu-id="9f91e-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="9f91e-114">Следующий пример <xref:System.Windows.Shapes.Rectangle> показывает другой, который удваивается в размерах; однако, <xref:System.Windows.Media.ScaleTransform> это имеет значение 25 для обоих <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и, <xref:System.Windows.Media.ScaleTransform.CenterY%2A>которое соответствует к центру прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9f91e-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="9f91e-115">Следующая иллюстрация показывает разницу между двумя <xref:System.Windows.Media.ScaleTransform> операциями.</span><span class="sxs-lookup"><span data-stu-id="9f91e-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="9f91e-116">Пунктирная линия показывает размер и положение прямоугольника до масштабирования.</span><span class="sxs-lookup"><span data-stu-id="9f91e-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="9f91e-117">![Двукратное масштабирование с разными центральными точками](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="9f91e-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="9f91e-118">Две операции ScaleTransform с одинаковыми значениями свойств ScaleX и ScaleY, но с разными центрами</span><span class="sxs-lookup"><span data-stu-id="9f91e-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="9f91e-119">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)</span><span class="sxs-lookup"><span data-stu-id="9f91e-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f91e-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9f91e-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="9f91e-121">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="9f91e-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="9f91e-122">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="9f91e-122">How-to Topics</span></span>](transformations-how-to-topics.md)
