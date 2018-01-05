---
title: "Практическое руководство. Использование свойства BetweenShowDelay"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfd4bb4c9e26361e5b8f573d06449b090497acd6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="88b62-102">Практическое руководство. Использование свойства BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="88b62-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="88b62-103">В этом примере показано, как использовать <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> свойства времени, чтобы подсказки отображаются быстро — с минимумом или совсем без задержки — при перемещении пользователем указателя мыши с одной подсказки непосредственно на другую.</span><span class="sxs-lookup"><span data-stu-id="88b62-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88b62-104">Пример</span><span class="sxs-lookup"><span data-stu-id="88b62-104">Example</span></span>  
 <span data-ttu-id="88b62-105">В следующем примере <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> свойству одной секунды (1000 миллисекунд) и <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> задано равным двум секундам (2000 мс) для подсказок обоих <xref:System.Windows.Shapes.Ellipse> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="88b62-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="88b62-106">Если отображается подсказка одного из эллипсов, затем наведите указатель мыши на другой эллипс в течение двух секунд и Пауза на нем подсказка второго эллипса отображается немедленно.</span><span class="sxs-lookup"><span data-stu-id="88b62-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="88b62-107">В любом из следующих сценариев <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> применяется, чего подсказка для второго эллипса ожидания одной секунды до появления:</span><span class="sxs-lookup"><span data-stu-id="88b62-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="88b62-108">Если время, необходимое для перемещения вторая кнопка является более двух секунд.</span><span class="sxs-lookup"><span data-stu-id="88b62-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="88b62-109">Если подсказка не отображается в начале временного интервала для первого эллипса.</span><span class="sxs-lookup"><span data-stu-id="88b62-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="88b62-110">См. также</span><span class="sxs-lookup"><span data-stu-id="88b62-110">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="88b62-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="88b62-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="88b62-112">Общие сведения о всплывающих подсказках</span><span class="sxs-lookup"><span data-stu-id="88b62-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
