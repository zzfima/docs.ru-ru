---
title: Стили и шаблоны элемента Slider
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283391"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="f08c1-102">Стили и шаблоны элемента Slider</span><span class="sxs-lookup"><span data-stu-id="f08c1-102">Slider Styles and Templates</span></span>
<span data-ttu-id="f08c1-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="f08c1-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f08c1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f08c1-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="f08c1-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="f08c1-106">Элементы Slider</span><span class="sxs-lookup"><span data-stu-id="f08c1-106">Slider Parts</span></span>  
 <span data-ttu-id="f08c1-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="f08c1-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="f08c1-108">Part</span></span>|<span data-ttu-id="f08c1-109">Тип</span><span class="sxs-lookup"><span data-stu-id="f08c1-109">Type</span></span>|<span data-ttu-id="f08c1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f08c1-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f08c1-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="f08c1-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="f08c1-112">Контейнер для элемента, указывающий расположение <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="f08c1-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="f08c1-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f08c1-114">Элемент, отображающий диапазон выбора по <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="f08c1-115">Диапазон выбора виден только в том случае, если свойство <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f08c1-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="f08c1-116">Состояния ползунка</span><span class="sxs-lookup"><span data-stu-id="f08c1-116">Slider States</span></span>  
 <span data-ttu-id="f08c1-117">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="f08c1-118">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="f08c1-118">VisualState Name</span></span>|<span data-ttu-id="f08c1-119">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f08c1-119">VisualStateGroup Name</span></span>|<span data-ttu-id="f08c1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f08c1-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f08c1-121">Нормальный</span><span class="sxs-lookup"><span data-stu-id="f08c1-121">Normal</span></span>|<span data-ttu-id="f08c1-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-122">CommonStates</span></span>|<span data-ttu-id="f08c1-123">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f08c1-123">The default state.</span></span>|  
|<span data-ttu-id="f08c1-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f08c1-124">MouseOver</span></span>|<span data-ttu-id="f08c1-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-125">CommonStates</span></span>|<span data-ttu-id="f08c1-126">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f08c1-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f08c1-127">Отключено.</span><span class="sxs-lookup"><span data-stu-id="f08c1-127">Disabled</span></span>|<span data-ttu-id="f08c1-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-128">CommonStates</span></span>|<span data-ttu-id="f08c1-129">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="f08c1-129">The control is disabled.</span></span>|  
|<span data-ttu-id="f08c1-130">Focused</span><span class="sxs-lookup"><span data-stu-id="f08c1-130">Focused</span></span>|<span data-ttu-id="f08c1-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-131">FocusStates</span></span>|<span data-ttu-id="f08c1-132">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="f08c1-132">The control has focus.</span></span>|  
|<span data-ttu-id="f08c1-133">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="f08c1-133">Unfocused</span></span>|<span data-ttu-id="f08c1-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-134">FocusStates</span></span>|<span data-ttu-id="f08c1-135">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="f08c1-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="f08c1-136">Допустимо</span><span class="sxs-lookup"><span data-stu-id="f08c1-136">Valid</span></span>|<span data-ttu-id="f08c1-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-137">ValidationStates</span></span>|<span data-ttu-id="f08c1-138">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="f08c1-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f08c1-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f08c1-139">InvalidFocused</span></span>|<span data-ttu-id="f08c1-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-140">ValidationStates</span></span>|<span data-ttu-id="f08c1-141">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="f08c1-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f08c1-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f08c1-142">InvalidUnfocused</span></span>|<span data-ttu-id="f08c1-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f08c1-143">ValidationStates</span></span>|<span data-ttu-id="f08c1-144">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="f08c1-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="f08c1-145">Пример элемента ControlTemplate ползунка</span><span class="sxs-lookup"><span data-stu-id="f08c1-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="f08c1-146">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="f08c1-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="f08c1-147">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f08c1-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f08c1-148">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f08c1-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08c1-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="f08c1-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f08c1-150">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="f08c1-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f08c1-151">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="f08c1-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f08c1-152">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="f08c1-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="f08c1-153">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="f08c1-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
