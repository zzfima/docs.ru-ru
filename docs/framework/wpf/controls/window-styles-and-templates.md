---
title: Стили и шаблоны элемента Window
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 9095405c47d4e113a2f0e7d572ba1209718f4b37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640086"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="64486-102">Стили и шаблоны элемента Window</span><span class="sxs-lookup"><span data-stu-id="64486-102">Window Styles and Templates</span></span>
<span data-ttu-id="64486-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64486-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="64486-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64486-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="64486-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="64486-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="64486-106">Элементы окна</span><span class="sxs-lookup"><span data-stu-id="64486-106">Window Parts</span></span>  
 <span data-ttu-id="64486-107"><xref:System.Windows.Window> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="64486-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="64486-108">Состояния окна</span><span class="sxs-lookup"><span data-stu-id="64486-108">Window States</span></span>  
 <span data-ttu-id="64486-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64486-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="64486-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="64486-110">VisualState Name</span></span>|<span data-ttu-id="64486-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="64486-111">VisualStateGroup Name</span></span>|<span data-ttu-id="64486-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="64486-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="64486-113">Valid</span><span class="sxs-lookup"><span data-stu-id="64486-113">Valid</span></span>|<span data-ttu-id="64486-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64486-114">ValidationStates</span></span>|<span data-ttu-id="64486-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="64486-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="64486-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="64486-116">InvalidFocused</span></span>|<span data-ttu-id="64486-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64486-117">ValidationStates</span></span>|<span data-ttu-id="64486-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="64486-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="64486-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="64486-119">InvalidUnfocused</span></span>|<span data-ttu-id="64486-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="64486-120">ValidationStates</span></span>|<span data-ttu-id="64486-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="64486-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="64486-122">Пример шаблона элемента управления окна</span><span class="sxs-lookup"><span data-stu-id="64486-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="64486-123">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64486-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="64486-124"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="64486-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="64486-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="64486-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64486-126">См. также</span><span class="sxs-lookup"><span data-stu-id="64486-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="64486-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="64486-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="64486-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="64486-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="64486-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="64486-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="64486-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="64486-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
