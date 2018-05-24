---
title: Стили и шаблоны элемента ToolTip
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 53b21f610ba957370fac70b79e6a827d624b6473
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="4d3d3-102">Стили и шаблоны элемента ToolTip</span><span class="sxs-lookup"><span data-stu-id="4d3d3-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="4d3d3-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ToolTip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="4d3d3-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4d3d3-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="4d3d3-106">Подсказка частей</span><span class="sxs-lookup"><span data-stu-id="4d3d3-106">ToolTip Parts</span></span>  
 <span data-ttu-id="4d3d3-107"><xref:System.Windows.Controls.ToolTip> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="4d3d3-108">Подсказка состояния</span><span class="sxs-lookup"><span data-stu-id="4d3d3-108">ToolTip States</span></span>  
 <span data-ttu-id="4d3d3-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ToolTip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="4d3d3-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="4d3d3-110">VisualState Name</span></span>|<span data-ttu-id="4d3d3-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4d3d3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4d3d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4d3d3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4d3d3-113">Closed</span><span class="sxs-lookup"><span data-stu-id="4d3d3-113">Closed</span></span>|<span data-ttu-id="4d3d3-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="4d3d3-114">OpenStates</span></span>|<span data-ttu-id="4d3d3-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-115">The default state.</span></span>|  
|<span data-ttu-id="4d3d3-116">Открыть</span><span class="sxs-lookup"><span data-stu-id="4d3d3-116">Open</span></span>|<span data-ttu-id="4d3d3-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="4d3d3-117">OpenStates</span></span>|<span data-ttu-id="4d3d3-118"><xref:System.Windows.Controls.ToolTip> Является видимым.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="4d3d3-119">Valid</span><span class="sxs-lookup"><span data-stu-id="4d3d3-119">Valid</span></span>|<span data-ttu-id="4d3d3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d3d3-120">ValidationStates</span></span>|<span data-ttu-id="4d3d3-121">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4d3d3-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4d3d3-122">InvalidFocused</span></span>|<span data-ttu-id="4d3d3-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d3d3-123">ValidationStates</span></span>|<span data-ttu-id="4d3d3-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4d3d3-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4d3d3-125">InvalidUnfocused</span></span>|<span data-ttu-id="4d3d3-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d3d3-126">ValidationStates</span></span>|<span data-ttu-id="4d3d3-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="4d3d3-128">Пример шаблона элемента управления всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="4d3d3-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="4d3d3-129">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ToolTip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="4d3d3-130">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4d3d3-131">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4d3d3-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3d3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4d3d3-132">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="4d3d3-133">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="4d3d3-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="4d3d3-134">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="4d3d3-134">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="4d3d3-135">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="4d3d3-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="4d3d3-136">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4d3d3-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
