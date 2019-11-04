---
title: Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459807"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="27d4a-102">Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления</span><span class="sxs-lookup"><span data-stu-id="27d4a-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="27d4a-103">В этом примере показано, как создать визуальный стиль фокуса в ресурсах и применить стиль к элементу управления с помощью свойства <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="27d4a-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d4a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="27d4a-104">Example</span></span>  
 <span data-ttu-id="27d4a-105">В следующем примере определяется стиль, который создает дополнительный набор элементов управления, который применяется только в том случае, если этот элемент управления имеет фокус ввода в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27d4a-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="27d4a-106">Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, а затем ссылки на этот стиль как на ресурс при задании свойства <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="27d4a-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="27d4a-107">Внешний прямоугольник, напоминающий границу, помещается за пределы прямоугольной области.</span><span class="sxs-lookup"><span data-stu-id="27d4a-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="27d4a-108">Если не было изменено иное, при изменении размера стиля используется <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, в котором применяется визуальный стиль фокуса.</span><span class="sxs-lookup"><span data-stu-id="27d4a-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="27d4a-109">В этом примере задаются отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A>, чтобы граница отображалась немного за пределами элемента управления.</span><span class="sxs-lookup"><span data-stu-id="27d4a-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="27d4a-110"><xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> дополняет любой стиль шаблона элемента управления, который поступает либо из явного стиля, либо из стиля темы. Основной стиль элемента управления по-прежнему можно создать с помощью <xref:System.Windows.Controls.ControlTemplate> и присвоив этому стилю значение свойства <xref:System.Windows.FrameworkElement.Style%2A>.</span><span class="sxs-lookup"><span data-stu-id="27d4a-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="27d4a-111">Визуальные стили фокуса должны постоянно использоваться в теме или пользовательском интерфейсе, вместо того чтобы использовать для каждого фокусного элемента другую.</span><span class="sxs-lookup"><span data-stu-id="27d4a-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="27d4a-112">Дополнительные сведения см. [в разделе Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="27d4a-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d4a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="27d4a-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="27d4a-114">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="27d4a-114">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="27d4a-115">Стилизация фокуса в элементах управления и FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="27d4a-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
