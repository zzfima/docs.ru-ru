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
ms.openlocfilehash: 8ec1f436ac0134ccdb19e63592c4181951814cb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375679"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="22729-102">Стили и шаблоны элемента Slider</span><span class="sxs-lookup"><span data-stu-id="22729-102">Slider Styles and Templates</span></span>
<span data-ttu-id="22729-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Slider> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="22729-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="22729-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="22729-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="22729-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="22729-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="22729-106">Ползунок частей</span><span class="sxs-lookup"><span data-stu-id="22729-106">Slider Parts</span></span>  
 <span data-ttu-id="22729-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Slider> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="22729-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="22729-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="22729-108">Part</span></span>|<span data-ttu-id="22729-109">Тип</span><span class="sxs-lookup"><span data-stu-id="22729-109">Type</span></span>|<span data-ttu-id="22729-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="22729-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="22729-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="22729-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="22729-112">Контейнер для элемента, который указывает положение <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="22729-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="22729-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="22729-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="22729-114">Элемент, отображаемый диапазон выбора вдоль <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="22729-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="22729-115">Диапазон выбора отображается только если <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> свойство `true`.</span><span class="sxs-lookup"><span data-stu-id="22729-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="22729-116">Состояния "ползунок"</span><span class="sxs-lookup"><span data-stu-id="22729-116">Slider States</span></span>  
 <span data-ttu-id="22729-117">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Slider> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="22729-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="22729-118">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="22729-118">VisualState Name</span></span>|<span data-ttu-id="22729-119">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="22729-119">VisualStateGroup Name</span></span>|<span data-ttu-id="22729-120">Описание</span><span class="sxs-lookup"><span data-stu-id="22729-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="22729-121">Норм.</span><span class="sxs-lookup"><span data-stu-id="22729-121">Normal</span></span>|<span data-ttu-id="22729-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22729-122">CommonStates</span></span>|<span data-ttu-id="22729-123">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22729-123">The default state.</span></span>|  
|<span data-ttu-id="22729-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="22729-124">MouseOver</span></span>|<span data-ttu-id="22729-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22729-125">CommonStates</span></span>|<span data-ttu-id="22729-126">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="22729-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="22729-127">Отключено</span><span class="sxs-lookup"><span data-stu-id="22729-127">Disabled</span></span>|<span data-ttu-id="22729-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="22729-128">CommonStates</span></span>|<span data-ttu-id="22729-129">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="22729-129">The control is disabled.</span></span>|  
|<span data-ttu-id="22729-130">Focused</span><span class="sxs-lookup"><span data-stu-id="22729-130">Focused</span></span>|<span data-ttu-id="22729-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="22729-131">FocusStates</span></span>|<span data-ttu-id="22729-132">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="22729-132">The control has focus.</span></span>|  
|<span data-ttu-id="22729-133">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="22729-133">Unfocused</span></span>|<span data-ttu-id="22729-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="22729-134">FocusStates</span></span>|<span data-ttu-id="22729-135">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="22729-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="22729-136">Valid</span><span class="sxs-lookup"><span data-stu-id="22729-136">Valid</span></span>|<span data-ttu-id="22729-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22729-137">ValidationStates</span></span>|<span data-ttu-id="22729-138">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="22729-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="22729-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="22729-139">InvalidFocused</span></span>|<span data-ttu-id="22729-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22729-140">ValidationStates</span></span>|<span data-ttu-id="22729-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="22729-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="22729-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="22729-142">InvalidUnfocused</span></span>|<span data-ttu-id="22729-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="22729-143">ValidationStates</span></span>|<span data-ttu-id="22729-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="22729-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="22729-145">Пример шаблона элемента управления "ползунок"</span><span class="sxs-lookup"><span data-stu-id="22729-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="22729-146">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Slider> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="22729-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="22729-147">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="22729-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="22729-148">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="22729-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22729-149">См. также</span><span class="sxs-lookup"><span data-stu-id="22729-149">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="22729-150">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="22729-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="22729-151">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="22729-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="22729-152">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="22729-152">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="22729-153">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="22729-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
