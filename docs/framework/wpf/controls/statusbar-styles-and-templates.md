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
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283372"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="d453b-102">Стили и шаблоны элемента StatusBar</span><span class="sxs-lookup"><span data-stu-id="d453b-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="d453b-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="d453b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="d453b-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d453b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d453b-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="d453b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="d453b-106">Части StatusBar</span><span class="sxs-lookup"><span data-stu-id="d453b-106">StatusBar Parts</span></span>  
 <span data-ttu-id="d453b-107">Элемент управления <xref:System.Windows.Controls.Primitives.StatusBar> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="d453b-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="d453b-108">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="d453b-108">StatusBar States</span></span>  
 <span data-ttu-id="d453b-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="d453b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="d453b-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d453b-110">VisualState Name</span></span>|<span data-ttu-id="d453b-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d453b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d453b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d453b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d453b-113">Valid</span><span class="sxs-lookup"><span data-stu-id="d453b-113">Valid</span></span>|<span data-ttu-id="d453b-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-114">ValidationStates</span></span>|<span data-ttu-id="d453b-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="d453b-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d453b-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d453b-116">InvalidFocused</span></span>|<span data-ttu-id="d453b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-117">ValidationStates</span></span>|<span data-ttu-id="d453b-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d453b-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d453b-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d453b-119">InvalidUnfocused</span></span>|<span data-ttu-id="d453b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-120">ValidationStates</span></span>|<span data-ttu-id="d453b-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d453b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="d453b-122">Статусбаритем части</span><span class="sxs-lookup"><span data-stu-id="d453b-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="d453b-123">Элемент управления <xref:System.Windows.Controls.Primitives.StatusBarItem> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="d453b-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="d453b-124">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="d453b-124">StatusBar States</span></span>  
 <span data-ttu-id="d453b-125">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.StatusBarItem>.</span><span class="sxs-lookup"><span data-stu-id="d453b-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="d453b-126">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d453b-126">VisualState Name</span></span>|<span data-ttu-id="d453b-127">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d453b-127">VisualStateGroup Name</span></span>|<span data-ttu-id="d453b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d453b-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d453b-129">Valid</span><span class="sxs-lookup"><span data-stu-id="d453b-129">Valid</span></span>|<span data-ttu-id="d453b-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-130">ValidationStates</span></span>|<span data-ttu-id="d453b-131">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="d453b-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d453b-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d453b-132">InvalidFocused</span></span>|<span data-ttu-id="d453b-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-133">ValidationStates</span></span>|<span data-ttu-id="d453b-134">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d453b-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d453b-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d453b-135">InvalidUnfocused</span></span>|<span data-ttu-id="d453b-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d453b-136">ValidationStates</span></span>|<span data-ttu-id="d453b-137">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d453b-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="d453b-138">Пример StatusBar ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d453b-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="d453b-139">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="d453b-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="d453b-140"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d453b-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d453b-141">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d453b-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d453b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="d453b-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d453b-143">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d453b-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d453b-144">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d453b-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d453b-145">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d453b-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d453b-146">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="d453b-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
