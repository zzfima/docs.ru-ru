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
ms.openlocfilehash: c2114a02016db96d898a394b6892b6d3042d81ff
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458236"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="f2492-102">Стили и шаблоны элемента Thumb</span><span class="sxs-lookup"><span data-stu-id="f2492-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="f2492-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f2492-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="f2492-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f2492-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f2492-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f2492-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="f2492-106">Элементы Thumb</span><span class="sxs-lookup"><span data-stu-id="f2492-106">Thumb Parts</span></span>

<span data-ttu-id="f2492-107">Элемент управления <xref:System.Windows.Controls.Primitives.Thumb> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="f2492-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="f2492-108">Состояния Thumb</span><span class="sxs-lookup"><span data-stu-id="f2492-108">Thumb States</span></span>

<span data-ttu-id="f2492-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f2492-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="f2492-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="f2492-110">VisualState Name</span></span>|<span data-ttu-id="f2492-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f2492-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f2492-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f2492-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="f2492-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="f2492-113">Normal</span></span>|<span data-ttu-id="f2492-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f2492-114">CommonStates</span></span>|<span data-ttu-id="f2492-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2492-115">The default state.</span></span>|
|<span data-ttu-id="f2492-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f2492-116">MouseOver</span></span>|<span data-ttu-id="f2492-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f2492-117">CommonStates</span></span>|<span data-ttu-id="f2492-118">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="f2492-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="f2492-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="f2492-119">Pressed</span></span>|<span data-ttu-id="f2492-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f2492-120">CommonStates</span></span>|<span data-ttu-id="f2492-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="f2492-121">The control is pressed.</span></span>|
|<span data-ttu-id="f2492-122">Отключено.</span><span class="sxs-lookup"><span data-stu-id="f2492-122">Disabled</span></span>|<span data-ttu-id="f2492-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f2492-123">CommonStates</span></span>|<span data-ttu-id="f2492-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="f2492-124">The control is disabled.</span></span>|
|<span data-ttu-id="f2492-125">Focused</span><span class="sxs-lookup"><span data-stu-id="f2492-125">Focused</span></span>|<span data-ttu-id="f2492-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f2492-126">FocusStates</span></span>|<span data-ttu-id="f2492-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="f2492-127">The control has focus.</span></span>|
|<span data-ttu-id="f2492-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="f2492-128">Unfocused</span></span>|<span data-ttu-id="f2492-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f2492-129">FocusStates</span></span>|<span data-ttu-id="f2492-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="f2492-130">The control does not have focus.</span></span>|
|<span data-ttu-id="f2492-131">Valid</span><span class="sxs-lookup"><span data-stu-id="f2492-131">Valid</span></span>|<span data-ttu-id="f2492-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f2492-132">ValidationStates</span></span>|<span data-ttu-id="f2492-133">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="f2492-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="f2492-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f2492-134">InvalidFocused</span></span>|<span data-ttu-id="f2492-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f2492-135">ValidationStates</span></span>|<span data-ttu-id="f2492-136">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="f2492-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="f2492-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f2492-137">InvalidUnfocused</span></span>|<span data-ttu-id="f2492-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f2492-138">ValidationStates</span></span>|<span data-ttu-id="f2492-139">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="f2492-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="f2492-140">Пример Thumb ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f2492-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="f2492-141">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f2492-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="f2492-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f2492-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="f2492-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f2492-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2492-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f2492-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f2492-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="f2492-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f2492-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="f2492-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f2492-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="f2492-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="f2492-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f2492-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
