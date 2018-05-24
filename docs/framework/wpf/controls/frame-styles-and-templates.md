---
title: Стили и шаблоны элемента Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 78bbeb915e17bcd59480b921efa1b6a51fa67762
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="1234f-102">Стили и шаблоны элемента Frame</span><span class="sxs-lookup"><span data-stu-id="1234f-102">Frame Styles and Templates</span></span>
<span data-ttu-id="1234f-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1234f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="1234f-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1234f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1234f-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="1234f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="1234f-106">Части фрейма</span><span class="sxs-lookup"><span data-stu-id="1234f-106">Frame Parts</span></span>  
 <span data-ttu-id="1234f-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1234f-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1234f-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="1234f-108">Part</span></span>|<span data-ttu-id="1234f-109">Тип</span><span class="sxs-lookup"><span data-stu-id="1234f-109">Type</span></span>|<span data-ttu-id="1234f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1234f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1234f-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="1234f-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="1234f-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="1234f-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="1234f-113">Состояния кадра</span><span class="sxs-lookup"><span data-stu-id="1234f-113">Frame States</span></span>  
 <span data-ttu-id="1234f-114">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1234f-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1234f-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="1234f-115">VisualState Name</span></span>|<span data-ttu-id="1234f-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1234f-116">VisualStateGroup Name</span></span>|<span data-ttu-id="1234f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1234f-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1234f-118">Valid</span><span class="sxs-lookup"><span data-stu-id="1234f-118">Valid</span></span>|<span data-ttu-id="1234f-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1234f-119">ValidationStates</span></span>|<span data-ttu-id="1234f-120">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="1234f-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1234f-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1234f-121">InvalidFocused</span></span>|<span data-ttu-id="1234f-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1234f-122">ValidationStates</span></span>|<span data-ttu-id="1234f-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1234f-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1234f-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1234f-124">InvalidUnfocused</span></span>|<span data-ttu-id="1234f-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1234f-125">ValidationStates</span></span>|<span data-ttu-id="1234f-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1234f-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="1234f-127">Пример создания шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="1234f-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="1234f-128">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1234f-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="1234f-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1234f-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1234f-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1234f-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1234f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1234f-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="1234f-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="1234f-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="1234f-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="1234f-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="1234f-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="1234f-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="1234f-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="1234f-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
