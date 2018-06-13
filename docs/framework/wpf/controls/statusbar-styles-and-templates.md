---
title: Стили и шаблоны элемента StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 11fa3ab6edd62f0b5484d9ccf76c101d04be353c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457869"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="e5fd0-102">Стили и шаблоны элемента StatusBar</span><span class="sxs-lookup"><span data-stu-id="e5fd0-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="e5fd0-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="e5fd0-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e5fd0-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e5fd0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="e5fd0-106">StatusBar частей</span><span class="sxs-lookup"><span data-stu-id="e5fd0-106">StatusBar Parts</span></span>  
 <span data-ttu-id="e5fd0-107"><xref:System.Windows.Controls.Primitives.StatusBar> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="e5fd0-108">Состояния Строка состояния</span><span class="sxs-lookup"><span data-stu-id="e5fd0-108">StatusBar States</span></span>  
 <span data-ttu-id="e5fd0-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="e5fd0-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e5fd0-110">VisualState Name</span></span>|<span data-ttu-id="e5fd0-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e5fd0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e5fd0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e5fd0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e5fd0-113">Valid</span><span class="sxs-lookup"><span data-stu-id="e5fd0-113">Valid</span></span>|<span data-ttu-id="e5fd0-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-114">ValidationStates</span></span>|<span data-ttu-id="e5fd0-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e5fd0-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e5fd0-116">InvalidFocused</span></span>|<span data-ttu-id="e5fd0-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-117">ValidationStates</span></span>|<span data-ttu-id="e5fd0-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e5fd0-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e5fd0-119">InvalidUnfocused</span></span>|<span data-ttu-id="e5fd0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-120">ValidationStates</span></span>|<span data-ttu-id="e5fd0-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="e5fd0-122">StatusBarItem частей</span><span class="sxs-lookup"><span data-stu-id="e5fd0-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="e5fd0-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="e5fd0-124">Состояния Строка состояния</span><span class="sxs-lookup"><span data-stu-id="e5fd0-124">StatusBar States</span></span>  
 <span data-ttu-id="e5fd0-125">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBarItem> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="e5fd0-126">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e5fd0-126">VisualState Name</span></span>|<span data-ttu-id="e5fd0-127">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e5fd0-127">VisualStateGroup Name</span></span>|<span data-ttu-id="e5fd0-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e5fd0-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e5fd0-129">Valid</span><span class="sxs-lookup"><span data-stu-id="e5fd0-129">Valid</span></span>|<span data-ttu-id="e5fd0-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-130">ValidationStates</span></span>|<span data-ttu-id="e5fd0-131">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e5fd0-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e5fd0-132">InvalidFocused</span></span>|<span data-ttu-id="e5fd0-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-133">ValidationStates</span></span>|<span data-ttu-id="e5fd0-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e5fd0-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e5fd0-135">InvalidUnfocused</span></span>|<span data-ttu-id="e5fd0-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5fd0-136">ValidationStates</span></span>|<span data-ttu-id="e5fd0-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="e5fd0-138">Пример шаблона элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="e5fd0-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e5fd0-139">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="e5fd0-140"><xref:System.Windows.Controls.ControlTemplate> Используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e5fd0-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e5fd0-141">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e5fd0-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fd0-142">См. также</span><span class="sxs-lookup"><span data-stu-id="e5fd0-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="e5fd0-143">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e5fd0-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="e5fd0-144">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e5fd0-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="e5fd0-145">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e5fd0-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="e5fd0-146">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e5fd0-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
