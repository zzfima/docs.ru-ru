---
title: "Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41895974b7e6c128d979e362f2dcef1c68e0a5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="aa3c3-102">Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления</span><span class="sxs-lookup"><span data-stu-id="aa3c3-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="aa3c3-103">В этом примере показано, как создать стиль визуального отображения фокуса в ресурсах и применение стиля к элементу управления с помощью <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa3c3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="aa3c3-104">Example</span></span>  
 <span data-ttu-id="aa3c3-105">В следующем примере определяется стиль, который создает дополнительный контроль композиции, только тогда, когда этот элемент управления получает фокус от клавиатуры в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa3c3-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="aa3c3-106">Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, то обращения этого стиля как ресурса при задании <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="aa3c3-107">Внешний прямоугольник, сходный с границей помещается за пределами прямоугольной области.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="aa3c3-108">В противном случае изменение размера стиля использует <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, где применяется стиль визуального отображения фокуса.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="aa3c3-109">Этот пример устанавливает отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A> вносить граница появлялась вне элемента управления с фокусом.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="aa3c3-110">Объект <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> является дополнением к любой стиля шаблона элемента управления, поступающие из явного стиля или тематического стиля; Основной стиль для элемента управления по-прежнему создаются с помощью <xref:System.Windows.Controls.ControlTemplate> и установив для этого стиля <xref:System.Windows.FrameworkElement.Style%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="aa3c3-111">Фокус визуальные стили следует использовать постоянно во всей темы или пользовательского интерфейса, вместо того чтобы использовать его для каждого элемента может иметь фокус.</span><span class="sxs-lookup"><span data-stu-id="aa3c3-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="aa3c3-112">Дополнительные сведения см. в разделе [стиля фокуса в элементах управления и стиля визуального отображения фокуса](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="aa3c3-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3c3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="aa3c3-113">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [<span data-ttu-id="aa3c3-114">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="aa3c3-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="aa3c3-115">Стилизация фокуса в элементах управления и FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="aa3c3-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
