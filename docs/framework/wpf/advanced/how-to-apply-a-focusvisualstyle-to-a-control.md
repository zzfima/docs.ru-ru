---
title: Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051329"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="4eaa3-102">Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления</span><span class="sxs-lookup"><span data-stu-id="4eaa3-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="4eaa3-103">В этом примере показано, как создать визуальный стиль фокуса в ресурсах и применить стиль к элементу управления с помощью <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eaa3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4eaa3-104">Example</span></span>  
 <span data-ttu-id="4eaa3-105">В следующем примере определяется стиль, который создает дополнительный контроль композиции, который применяется, только если этот элемент управления получает фокус от клавиатуры в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eaa3-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="4eaa3-106">Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, то ссылки на этот стиль как ресурс, при задании <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="4eaa3-107">Внешний прямоугольник, сходный с границей помещается за пределами прямоугольной области.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="4eaa3-108">В противном случае изменение размера стиля использует <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, где применяется визуальный стиль фокуса.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="4eaa3-109">В этом примере задает отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A> чтобы сделать границу немного находиться за пределами элемента управления с фокусом.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="4eaa3-110">Объект <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> является дополнением к любой стиль шаблона элемента управления, поступающие из явного стиля или стиля темы; основной стиль для элемента управления можно по-прежнему создаваться с помощью <xref:System.Windows.Controls.ControlTemplate> и установив для этого стиля <xref:System.Windows.FrameworkElement.Style%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="4eaa3-111">Фокус, визуальные стили должен последовательно использоваться между тем и пользовательский Интерфейс, вместо того чтобы использовать его для каждого элемента, способному получать фокус.</span><span class="sxs-lookup"><span data-stu-id="4eaa3-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="4eaa3-112">Дополнительные сведения см. в разделе [Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="4eaa3-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eaa3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4eaa3-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="4eaa3-114">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="4eaa3-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="4eaa3-115">Стилизация фокуса в элементах управления и FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="4eaa3-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
