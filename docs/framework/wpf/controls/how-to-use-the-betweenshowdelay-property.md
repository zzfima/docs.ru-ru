---
title: Практическое руководство. Использование свойства BetweenShowDelay
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614533"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="a9736-102">Практическое руководство. Использование свойства BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="a9736-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="a9736-103">В этом примере показано, как использовать <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> свойства времени, чтобы подсказки отображаются быстро — с минимальными задержками или без, когда пользователь перемещает указатель мыши из одна подсказка непосредственно в другой.</span><span class="sxs-lookup"><span data-stu-id="a9736-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9736-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a9736-104">Example</span></span>  
 <span data-ttu-id="a9736-105">В следующем примере <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> свойству одну секунду (1000 миллисекунд) и <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> задано значение двух секунд (2000 мс) для подсказок обоих <xref:System.Windows.Shapes.Ellipse> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a9736-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="a9736-106">Если отображение всплывающей подсказки для одного из эллипсов и затем наведите указатель мыши на другой эллипс в две секунды и приостановки на нем, сразу же появляется подсказка второго эллипса.</span><span class="sxs-lookup"><span data-stu-id="a9736-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="a9736-107">В любом из следующих сценариев <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> применяется, чего подсказка для второго эллипса ожидания одной секунды до появления:</span><span class="sxs-lookup"><span data-stu-id="a9736-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="a9736-108">Если время, необходимое для перемещения вторая кнопка является более двух секунд.</span><span class="sxs-lookup"><span data-stu-id="a9736-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="a9736-109">Если подсказка не отображается в начале периода времени, для первого эллипса.</span><span class="sxs-lookup"><span data-stu-id="a9736-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="a9736-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a9736-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="a9736-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="a9736-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="a9736-112">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="a9736-112">ToolTip Overview</span></span>](tooltip-overview.md)
