---
title: "Практическое руководство. Масштабирование элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2bff810dc9b44b25db93c8565da27acc4f0ccc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="7e263-102">Практическое руководство. Масштабирование элемента</span><span class="sxs-lookup"><span data-stu-id="7e263-102">How to: Scale an Element</span></span>
<span data-ttu-id="7e263-103">В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> для масштабирования элемента.</span><span class="sxs-lookup"><span data-stu-id="7e263-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="7e263-104">Используйте <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства для изменения размеров элемента с определенным коэффициентом.</span><span class="sxs-lookup"><span data-stu-id="7e263-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="7e263-105">Например <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> значение 1,5 увеличивает элемент на 150 процентов от его исходной ширины.</span><span class="sxs-lookup"><span data-stu-id="7e263-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="7e263-106">Объект <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> значение 0,5 сжимает высота элемента на 50%.</span><span class="sxs-lookup"><span data-stu-id="7e263-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="7e263-107">Используйте <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A> свойства, чтобы указать точку, в центре операция масштабирования.</span><span class="sxs-lookup"><span data-stu-id="7e263-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="7e263-108">По умолчанию <xref:System.Windows.Media.ScaleTransform> центрируется в точке (0,0), которое соответствует значению верхнего левого угла прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="7e263-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="7e263-109">Это приводит к перемещению элемента, а также делает его размер больше, поскольку при применении <xref:System.Windows.Media.Transform>, изменить пространство координат, в которой находится объект.</span><span class="sxs-lookup"><span data-stu-id="7e263-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="7e263-110">В следующем примере используется <xref:System.Windows.Media.ScaleTransform> удвоить размер 50 на 50 <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="7e263-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="7e263-111"><xref:System.Windows.Media.ScaleTransform> Имеет значение 0 (по умолчанию) для <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e263-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e263-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7e263-112">Example</span></span>  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="7e263-113">Обычно задается <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A> к центру масштабируемого объекта: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="7e263-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="7e263-114">В следующем примере показано другой <xref:System.Windows.Shapes.Rectangle> , в два раза в размере; тем не менее, это <xref:System.Windows.Media.ScaleTransform> имеет значение 25 для <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, который соответствует центру прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="7e263-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="7e263-115">Ниже показано различие между этими двумя <xref:System.Windows.Media.ScaleTransform> операций.</span><span class="sxs-lookup"><span data-stu-id="7e263-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="7e263-116">Пунктирная линия показывает размер и положение прямоугольника до масштабирования.</span><span class="sxs-lookup"><span data-stu-id="7e263-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="7e263-117">![масштабирование на 2 с различными точками центра](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="7e263-117">![2x scales with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="7e263-118">Две операции ScaleTransform с одинаковыми значениями свойств ScaleX и ScaleY, но с разными центрами</span><span class="sxs-lookup"><span data-stu-id="7e263-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="7e263-119">Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="7e263-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e263-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7e263-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="7e263-121">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="7e263-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="7e263-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="7e263-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
