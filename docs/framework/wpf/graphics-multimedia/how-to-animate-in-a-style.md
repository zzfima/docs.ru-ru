---
title: "Практическое руководство. Применение анимации в стиле"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="7d3fc-102">Практическое руководство. Применение анимации в стиле</span><span class="sxs-lookup"><span data-stu-id="7d3fc-102">How to: Animate in a Style</span></span>
<span data-ttu-id="7d3fc-103">В этом примере показано, как для анимации свойства в стиле.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="7d3fc-104">При анимации в стиле элемент framework, для которого определен стиль можно применить напрямую.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="7d3fc-105">Целевой объект freezable, вам необходимо «поставить точку» из свойства элемента со стилем.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="7d3fc-106">В следующем примере несколько анимаций определены в стиле и применены к <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="7d3fc-107">Когда пользователь перемещает указатель мыши на кнопку, его из непрозрачного переходит в частично полупрозрачные и обратно еще раз, многократно.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="7d3fc-108">При наведении указателя мыши с кнопки, она становится полностью непрозрачной.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="7d3fc-109">При нажатии кнопки цвет ее фона меняется с оранжевого на белый и обратно.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="7d3fc-110">Поскольку <xref:System.Windows.Media.SolidColorBrush> используется для рисования кнопки нельзя обращаться непосредственно, она осуществляется вниз с помощью кнопки <xref:System.Windows.Controls.Control.Background%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d3fc-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7d3fc-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="7d3fc-112">Обратите внимание, что при анимации с использованием стиля, возможных в целевые объекты, которые не существуют.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="7d3fc-113">Например, предположим, что стиль использует <xref:System.Windows.Media.SolidColorBrush> переопределяется, чтобы задать свойства фона кнопки, но в некоторый момент стиль и цвет фона кнопки устанавливается с <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="7d3fc-114">При попытке анимации <xref:System.Windows.Media.SolidColorBrush> не создается исключение; анимация не выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="7d3fc-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="7d3fc-115">Дополнительные сведения о синтаксисе планирования раскадровки см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d3fc-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="7d3fc-116">Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d3fc-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="7d3fc-117">Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="7d3fc-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
