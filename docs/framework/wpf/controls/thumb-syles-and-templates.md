---
title: Стили и шаблоны элемента Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 16204820f18fed87ab769f3f59c10a35c4048d29
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="d755b-102">Стили и шаблоны элемента Thumb</span><span class="sxs-lookup"><span data-stu-id="d755b-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="d755b-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d755b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="d755b-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d755b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d755b-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d755b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="d755b-106">Бегунок частей</span><span class="sxs-lookup"><span data-stu-id="d755b-106">Thumb Parts</span></span>  
 <span data-ttu-id="d755b-107"><xref:System.Windows.Controls.Primitives.Thumb> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="d755b-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="d755b-108">Бегунок состояний</span><span class="sxs-lookup"><span data-stu-id="d755b-108">Thumb States</span></span>  
 <span data-ttu-id="d755b-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d755b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="d755b-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d755b-110">VisualState Name</span></span>|<span data-ttu-id="d755b-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d755b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d755b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d755b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d755b-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="d755b-113">Normal</span></span>|<span data-ttu-id="d755b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d755b-114">CommonStates</span></span>|<span data-ttu-id="d755b-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d755b-115">The default state.</span></span>|  
|<span data-ttu-id="d755b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d755b-116">MouseOver</span></span>|<span data-ttu-id="d755b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d755b-117">CommonStates</span></span>|<span data-ttu-id="d755b-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d755b-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d755b-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="d755b-119">Pressed</span></span>|<span data-ttu-id="d755b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d755b-120">CommonStates</span></span>|<span data-ttu-id="d755b-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="d755b-121">The control is pressed.</span></span>|  
|<span data-ttu-id="d755b-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="d755b-122">Disabled</span></span>|<span data-ttu-id="d755b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d755b-123">CommonStates</span></span>|<span data-ttu-id="d755b-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="d755b-124">The control is disabled.</span></span>|  
|<span data-ttu-id="d755b-125">Focused</span><span class="sxs-lookup"><span data-stu-id="d755b-125">Focused</span></span>|<span data-ttu-id="d755b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d755b-126">FocusStates</span></span>|<span data-ttu-id="d755b-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d755b-127">The control has focus.</span></span>|  
|<span data-ttu-id="d755b-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="d755b-128">Unfocused</span></span>|<span data-ttu-id="d755b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d755b-129">FocusStates</span></span>|<span data-ttu-id="d755b-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d755b-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="d755b-131">Valid</span><span class="sxs-lookup"><span data-stu-id="d755b-131">Valid</span></span>|<span data-ttu-id="d755b-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d755b-132">ValidationStates</span></span>|<span data-ttu-id="d755b-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="d755b-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d755b-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d755b-134">InvalidFocused</span></span>|<span data-ttu-id="d755b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d755b-135">ValidationStates</span></span>|<span data-ttu-id="d755b-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d755b-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d755b-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d755b-137">InvalidUnfocused</span></span>|<span data-ttu-id="d755b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d755b-138">ValidationStates</span></span>|<span data-ttu-id="d755b-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d755b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="d755b-140">Пример шаблона элемента управления "бегунок"</span><span class="sxs-lookup"><span data-stu-id="d755b-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="d755b-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d755b-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="d755b-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d755b-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d755b-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d755b-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d755b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d755b-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d755b-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d755b-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d755b-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d755b-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d755b-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d755b-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d755b-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d755b-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
