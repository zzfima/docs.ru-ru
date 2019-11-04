---
title: Стили и шаблоны элемента Button
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 64764d43191d30c191c5d6519982b16cfc86d26e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460951"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="3d930-102">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="3d930-102">Button Styles and Templates</span></span>
<span data-ttu-id="3d930-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="3d930-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="3d930-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3d930-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3d930-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="3d930-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="3d930-106">Части кнопки</span><span class="sxs-lookup"><span data-stu-id="3d930-106">Button Parts</span></span>  
 <span data-ttu-id="3d930-107">Элемент управления <xref:System.Windows.Controls.Button> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="3d930-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="3d930-108">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="3d930-108">Button States</span></span>  
 <span data-ttu-id="3d930-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="3d930-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="3d930-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="3d930-110">VisualState Name</span></span>|<span data-ttu-id="3d930-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3d930-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3d930-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3d930-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3d930-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="3d930-113">Normal</span></span>|<span data-ttu-id="3d930-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3d930-114">CommonStates</span></span>|<span data-ttu-id="3d930-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3d930-115">The default state.</span></span>|  
|<span data-ttu-id="3d930-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3d930-116">MouseOver</span></span>|<span data-ttu-id="3d930-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3d930-117">CommonStates</span></span>|<span data-ttu-id="3d930-118">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d930-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="3d930-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="3d930-119">Pressed</span></span>|<span data-ttu-id="3d930-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3d930-120">CommonStates</span></span>|<span data-ttu-id="3d930-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="3d930-121">The control is pressed.</span></span>|  
|<span data-ttu-id="3d930-122">Отключено.</span><span class="sxs-lookup"><span data-stu-id="3d930-122">Disabled</span></span>|<span data-ttu-id="3d930-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3d930-123">CommonStates</span></span>|<span data-ttu-id="3d930-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="3d930-124">The control is disabled.</span></span>|  
|<span data-ttu-id="3d930-125">Focused</span><span class="sxs-lookup"><span data-stu-id="3d930-125">Focused</span></span>|<span data-ttu-id="3d930-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3d930-126">FocusStates</span></span>|<span data-ttu-id="3d930-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3d930-127">The control has focus.</span></span>|  
|<span data-ttu-id="3d930-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="3d930-128">Unfocused</span></span>|<span data-ttu-id="3d930-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3d930-129">FocusStates</span></span>|<span data-ttu-id="3d930-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="3d930-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="3d930-131">Valid</span><span class="sxs-lookup"><span data-stu-id="3d930-131">Valid</span></span>|<span data-ttu-id="3d930-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d930-132">ValidationStates</span></span>|<span data-ttu-id="3d930-133">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="3d930-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3d930-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3d930-134">InvalidFocused</span></span>|<span data-ttu-id="3d930-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d930-135">ValidationStates</span></span>|<span data-ttu-id="3d930-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3d930-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="3d930-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3d930-137">InvalidUnfocused</span></span>|<span data-ttu-id="3d930-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3d930-138">ValidationStates</span></span>|<span data-ttu-id="3d930-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="3d930-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="3d930-140">Пример ControlTemplate для кнопки</span><span class="sxs-lookup"><span data-stu-id="3d930-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="3d930-141">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="3d930-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="3d930-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3d930-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3d930-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3d930-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d930-144">См. также</span><span class="sxs-lookup"><span data-stu-id="3d930-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3d930-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="3d930-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3d930-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="3d930-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3d930-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="3d930-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3d930-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="3d930-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
