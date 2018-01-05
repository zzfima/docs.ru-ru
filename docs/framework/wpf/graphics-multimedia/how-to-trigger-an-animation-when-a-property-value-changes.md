---
title: "Практическое руководство. Запуск анимации при изменении значения свойства"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0eb4542d8baf86f01417eb1925028a00471b40b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="89caa-102">Практическое руководство. Запуск анимации при изменении значения свойства</span><span class="sxs-lookup"><span data-stu-id="89caa-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="89caa-103">В этом примере показано, как использовать <xref:System.Windows.Trigger> запуск <xref:System.Windows.Media.Animation.Storyboard> при изменении значения свойства.</span><span class="sxs-lookup"><span data-stu-id="89caa-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="89caa-104">Можно использовать <xref:System.Windows.Trigger> внутри <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, или <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="89caa-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89caa-105">Пример</span><span class="sxs-lookup"><span data-stu-id="89caa-105">Example</span></span>  
 <span data-ttu-id="89caa-106">В следующем примере используется <xref:System.Windows.Trigger> для анимации <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Button> при его <xref:System.Windows.UIElement.IsMouseOver%2A> свойство становится `true`.</span><span class="sxs-lookup"><span data-stu-id="89caa-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="89caa-107">Анимации с помощью свойства <xref:System.Windows.Trigger> объекты ведут себя в сложнее, чем <xref:System.Windows.EventTrigger> анимации или анимации работы с использованием <xref:System.Windows.Media.Animation.Storyboard> методов.</span><span class="sxs-lookup"><span data-stu-id="89caa-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="89caa-108">Они «передаваться» с анимацией определенные другими <xref:System.Windows.Trigger> объектов, но объединено <xref:System.Windows.EventTrigger> и запустить метод анимации.</span><span class="sxs-lookup"><span data-stu-id="89caa-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89caa-109">См. также</span><span class="sxs-lookup"><span data-stu-id="89caa-109">See Also</span></span>  
 <xref:System.Windows.Trigger>  
 [<span data-ttu-id="89caa-110">Общие сведения о методах анимации свойств</span><span class="sxs-lookup"><span data-stu-id="89caa-110">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="89caa-111">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="89caa-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
