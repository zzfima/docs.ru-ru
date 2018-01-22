---
title: "Практическое руководство. Настройка делений на ползунке"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d21d2950ed228bf588a202419c222ee86dde5b0d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="83dc9-102">Практическое руководство. Настройка делений на ползунке</span><span class="sxs-lookup"><span data-stu-id="83dc9-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="83dc9-103">В этом примере показано, как создать <xref:System.Windows.Controls.Slider> элемента управления, содержащего деления.</span><span class="sxs-lookup"><span data-stu-id="83dc9-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83dc9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="83dc9-104">Example</span></span>  
 <span data-ttu-id="83dc9-105"><xref:System.Windows.Controls.Primitives.TickBar> Отображается при установке <xref:System.Windows.Controls.Slider.TickPlacement%2A> свойство в значение, отличное от <xref:System.Windows.Controls.Primitives.TickPlacement.None>, который является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83dc9-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="83dc9-106">В следующем примере показано, как создать <xref:System.Windows.Controls.Slider> с <xref:System.Windows.Controls.Primitives.TickBar> отображает метки деления.</span><span class="sxs-lookup"><span data-stu-id="83dc9-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="83dc9-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A> И <xref:System.Windows.Controls.Slider.TickFrequency%2A> определяют расположение делений и интервал между ними.</span><span class="sxs-lookup"><span data-stu-id="83dc9-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="83dc9-108">При перемещении <xref:System.Windows.Controls.Primitives.Thumb>, всплывающие подсказки отображают значение <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="83dc9-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="83dc9-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Свойство определяет, где появляется подсказка.</span><span class="sxs-lookup"><span data-stu-id="83dc9-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="83dc9-110"><xref:System.Windows.Controls.Primitives.Thumb> Перемещений соответствуют расположение делений, так как <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> равно `true`.</span><span class="sxs-lookup"><span data-stu-id="83dc9-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="83dc9-111">В следующем примере показано, как использовать <xref:System.Windows.Controls.Slider.Ticks%2A> свойства для создания метки вдоль деления <xref:System.Windows.Controls.Slider> через нерегулярные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="83dc9-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="83dc9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="83dc9-112">See Also</span></span>  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [<span data-ttu-id="83dc9-113">Практические руководства, посвященные элементу управления Slider</span><span class="sxs-lookup"><span data-stu-id="83dc9-113">Slider How-to Topics</span></span>](http://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
