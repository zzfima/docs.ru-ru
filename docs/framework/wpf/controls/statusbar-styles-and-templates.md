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
ms.openlocfilehash: b1dd575d58571b845fc849ca432ad440d1ce3ec4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458263"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="fa72c-102">Стили и шаблоны элемента StatusBar</span><span class="sxs-lookup"><span data-stu-id="fa72c-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="fa72c-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="fa72c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="fa72c-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa72c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fa72c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="fa72c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="fa72c-106">Части StatusBar</span><span class="sxs-lookup"><span data-stu-id="fa72c-106">StatusBar Parts</span></span>  
 <span data-ttu-id="fa72c-107">Элемент управления <xref:System.Windows.Controls.Primitives.StatusBar> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="fa72c-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="fa72c-108">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="fa72c-108">StatusBar States</span></span>  
 <span data-ttu-id="fa72c-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="fa72c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="fa72c-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="fa72c-110">VisualState Name</span></span>|<span data-ttu-id="fa72c-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fa72c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fa72c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fa72c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fa72c-113">Valid</span><span class="sxs-lookup"><span data-stu-id="fa72c-113">Valid</span></span>|<span data-ttu-id="fa72c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-114">ValidationStates</span></span>|<span data-ttu-id="fa72c-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="fa72c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fa72c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fa72c-116">InvalidFocused</span></span>|<span data-ttu-id="fa72c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-117">ValidationStates</span></span>|<span data-ttu-id="fa72c-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="fa72c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fa72c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fa72c-119">InvalidUnfocused</span></span>|<span data-ttu-id="fa72c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-120">ValidationStates</span></span>|<span data-ttu-id="fa72c-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="fa72c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="fa72c-122">Статусбаритем части</span><span class="sxs-lookup"><span data-stu-id="fa72c-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="fa72c-123">Элемент управления <xref:System.Windows.Controls.Primitives.StatusBarItem> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="fa72c-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="fa72c-124">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="fa72c-124">StatusBar States</span></span>  
 <span data-ttu-id="fa72c-125">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.StatusBarItem>.</span><span class="sxs-lookup"><span data-stu-id="fa72c-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="fa72c-126">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="fa72c-126">VisualState Name</span></span>|<span data-ttu-id="fa72c-127">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fa72c-127">VisualStateGroup Name</span></span>|<span data-ttu-id="fa72c-128">Описание</span><span class="sxs-lookup"><span data-stu-id="fa72c-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fa72c-129">Valid</span><span class="sxs-lookup"><span data-stu-id="fa72c-129">Valid</span></span>|<span data-ttu-id="fa72c-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-130">ValidationStates</span></span>|<span data-ttu-id="fa72c-131">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="fa72c-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fa72c-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fa72c-132">InvalidFocused</span></span>|<span data-ttu-id="fa72c-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-133">ValidationStates</span></span>|<span data-ttu-id="fa72c-134">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="fa72c-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fa72c-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fa72c-135">InvalidUnfocused</span></span>|<span data-ttu-id="fa72c-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fa72c-136">ValidationStates</span></span>|<span data-ttu-id="fa72c-137">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="fa72c-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="fa72c-138">Пример StatusBar ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fa72c-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="fa72c-139">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="fa72c-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="fa72c-140"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fa72c-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fa72c-141">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fa72c-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa72c-142">См. также</span><span class="sxs-lookup"><span data-stu-id="fa72c-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fa72c-143">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="fa72c-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fa72c-144">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="fa72c-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fa72c-145">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="fa72c-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="fa72c-146">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fa72c-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
