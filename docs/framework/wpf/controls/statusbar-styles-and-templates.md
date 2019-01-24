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
ms.openlocfilehash: ee3bd060268d5ab6f713a74f871d7de0dd77782b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660467"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="b1b6b-102">Стили и шаблоны элемента StatusBar</span><span class="sxs-lookup"><span data-stu-id="b1b6b-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="b1b6b-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="b1b6b-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b1b6b-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b1b6b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="b1b6b-106">StatusBar частей</span><span class="sxs-lookup"><span data-stu-id="b1b6b-106">StatusBar Parts</span></span>  
 <span data-ttu-id="b1b6b-107"><xref:System.Windows.Controls.Primitives.StatusBar> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="b1b6b-108">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="b1b6b-108">StatusBar States</span></span>  
 <span data-ttu-id="b1b6b-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="b1b6b-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="b1b6b-110">VisualState Name</span></span>|<span data-ttu-id="b1b6b-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b1b6b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b1b6b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1b6b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b1b6b-113">Valid</span><span class="sxs-lookup"><span data-stu-id="b1b6b-113">Valid</span></span>|<span data-ttu-id="b1b6b-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-114">ValidationStates</span></span>|<span data-ttu-id="b1b6b-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b1b6b-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b1b6b-116">InvalidFocused</span></span>|<span data-ttu-id="b1b6b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-117">ValidationStates</span></span>|<span data-ttu-id="b1b6b-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b1b6b-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b1b6b-119">InvalidUnfocused</span></span>|<span data-ttu-id="b1b6b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-120">ValidationStates</span></span>|<span data-ttu-id="b1b6b-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="b1b6b-122">Элемент управления StatusBarItem частей</span><span class="sxs-lookup"><span data-stu-id="b1b6b-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="b1b6b-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="b1b6b-124">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="b1b6b-124">StatusBar States</span></span>  
 <span data-ttu-id="b1b6b-125">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBarItem> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="b1b6b-126">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="b1b6b-126">VisualState Name</span></span>|<span data-ttu-id="b1b6b-127">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b1b6b-127">VisualStateGroup Name</span></span>|<span data-ttu-id="b1b6b-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="b1b6b-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b1b6b-129">Valid</span><span class="sxs-lookup"><span data-stu-id="b1b6b-129">Valid</span></span>|<span data-ttu-id="b1b6b-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-130">ValidationStates</span></span>|<span data-ttu-id="b1b6b-131">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b1b6b-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b1b6b-132">InvalidFocused</span></span>|<span data-ttu-id="b1b6b-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-133">ValidationStates</span></span>|<span data-ttu-id="b1b6b-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b1b6b-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b1b6b-135">InvalidUnfocused</span></span>|<span data-ttu-id="b1b6b-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b1b6b-136">ValidationStates</span></span>|<span data-ttu-id="b1b6b-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="b1b6b-138">Пример шаблона элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="b1b6b-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="b1b6b-139">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="b1b6b-140"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1b6b-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b1b6b-141">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b1b6b-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b6b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b6b-142">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b1b6b-143">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="b1b6b-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="b1b6b-144">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="b1b6b-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="b1b6b-145">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="b1b6b-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="b1b6b-146">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b1b6b-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
