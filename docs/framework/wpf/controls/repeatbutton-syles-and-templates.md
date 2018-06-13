---
title: Стили и шаблоны элемента RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: d5edea14c1ea4184fda67e9b64887f192420b413
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457155"
---
# <a name="repeatbutton-syles-and-templates"></a><span data-ttu-id="48951-102">Стили и шаблоны элемента RepeatButton</span><span class="sxs-lookup"><span data-stu-id="48951-102">RepeatButton Syles and Templates</span></span>
<span data-ttu-id="48951-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48951-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="48951-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48951-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="48951-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="48951-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="repeatbutton-parts"></a><span data-ttu-id="48951-106">RepeatButton частей</span><span class="sxs-lookup"><span data-stu-id="48951-106">RepeatButton Parts</span></span>  
 <span data-ttu-id="48951-107"><xref:System.Windows.Controls.Primitives.RepeatButton> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="48951-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>  
  
## <a name="repeatbutton-states"></a><span data-ttu-id="48951-108">RepeatButton состояний</span><span class="sxs-lookup"><span data-stu-id="48951-108">RepeatButton States</span></span>  
 <span data-ttu-id="48951-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48951-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
|<span data-ttu-id="48951-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="48951-110">VisualState Name</span></span>|<span data-ttu-id="48951-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="48951-111">VisualStateGroup Name</span></span>|<span data-ttu-id="48951-112">Описание</span><span class="sxs-lookup"><span data-stu-id="48951-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="48951-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="48951-113">Normal</span></span>|<span data-ttu-id="48951-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48951-114">CommonStates</span></span>|<span data-ttu-id="48951-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48951-115">The default state.</span></span>|  
|<span data-ttu-id="48951-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="48951-116">MouseOver</span></span>|<span data-ttu-id="48951-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48951-117">CommonStates</span></span>|<span data-ttu-id="48951-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="48951-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="48951-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="48951-119">Pressed</span></span>|<span data-ttu-id="48951-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48951-120">CommonStates</span></span>|<span data-ttu-id="48951-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="48951-121">The control is pressed.</span></span>|  
|<span data-ttu-id="48951-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="48951-122">Disabled</span></span>|<span data-ttu-id="48951-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48951-123">CommonStates</span></span>|<span data-ttu-id="48951-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="48951-124">The control is disabled.</span></span>|  
|<span data-ttu-id="48951-125">Focused</span><span class="sxs-lookup"><span data-stu-id="48951-125">Focused</span></span>|<span data-ttu-id="48951-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="48951-126">FocusStates</span></span>|<span data-ttu-id="48951-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="48951-127">The control has focus.</span></span>|  
|<span data-ttu-id="48951-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="48951-128">Unfocused</span></span>|<span data-ttu-id="48951-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="48951-129">FocusStates</span></span>|<span data-ttu-id="48951-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="48951-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="48951-131">Valid</span><span class="sxs-lookup"><span data-stu-id="48951-131">Valid</span></span>|<span data-ttu-id="48951-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48951-132">ValidationStates</span></span>|<span data-ttu-id="48951-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="48951-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="48951-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="48951-134">InvalidFocused</span></span>|<span data-ttu-id="48951-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48951-135">ValidationStates</span></span>|<span data-ttu-id="48951-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="48951-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="48951-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="48951-137">InvalidUnfocused</span></span>|<span data-ttu-id="48951-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48951-138">ValidationStates</span></span>|<span data-ttu-id="48951-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="48951-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="48951-140">Пример шаблона элемента управления RepeatButton</span><span class="sxs-lookup"><span data-stu-id="48951-140">RepeatButton ControlTemplate Example</span></span>  
 <span data-ttu-id="48951-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48951-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RepeatButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]  
  
 <span data-ttu-id="48951-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="48951-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="48951-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="48951-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48951-144">См. также</span><span class="sxs-lookup"><span data-stu-id="48951-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="48951-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="48951-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="48951-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="48951-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="48951-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="48951-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="48951-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="48951-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
