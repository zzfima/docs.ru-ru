---
title: Элемент управления ToggleButton стили и шаблоны
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 46fd7d07c3904ee752ae3f467f65af4b0c031c84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509513"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="5dfd6-102">Элемент управления ToggleButton стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="5dfd6-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="5dfd6-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="5dfd6-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5dfd6-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="5dfd6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="5dfd6-106">Элемент управления ToggleButton частей</span><span class="sxs-lookup"><span data-stu-id="5dfd6-106">ToggleButton Parts</span></span>

<span data-ttu-id="5dfd6-107"><xref:System.Windows.Controls.Primitives.ToggleButton> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="5dfd6-108">Элемент управления ToggleButton состояний</span><span class="sxs-lookup"><span data-stu-id="5dfd6-108">ToggleButton States</span></span>

<span data-ttu-id="5dfd6-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="5dfd6-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="5dfd6-110">VisualState Name</span></span>|<span data-ttu-id="5dfd6-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5dfd6-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5dfd6-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="5dfd6-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="5dfd6-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-113">Normal</span></span>|<span data-ttu-id="5dfd6-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-114">CommonStates</span></span>|<span data-ttu-id="5dfd6-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-115">The default state.</span></span>|
|<span data-ttu-id="5dfd6-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5dfd6-116">MouseOver</span></span>|<span data-ttu-id="5dfd6-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-117">CommonStates</span></span>|<span data-ttu-id="5dfd6-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="5dfd6-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="5dfd6-119">Pressed</span></span>|<span data-ttu-id="5dfd6-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-120">CommonStates</span></span>|<span data-ttu-id="5dfd6-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-121">The control is pressed.</span></span>|
|<span data-ttu-id="5dfd6-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="5dfd6-122">Disabled</span></span>|<span data-ttu-id="5dfd6-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-123">CommonStates</span></span>|<span data-ttu-id="5dfd6-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-124">The control is disabled.</span></span>|
|<span data-ttu-id="5dfd6-125">Focused</span><span class="sxs-lookup"><span data-stu-id="5dfd6-125">Focused</span></span>|<span data-ttu-id="5dfd6-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-126">FocusStates</span></span>|<span data-ttu-id="5dfd6-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-127">The control has focus.</span></span>|
|<span data-ttu-id="5dfd6-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="5dfd6-128">Unfocused</span></span>|<span data-ttu-id="5dfd6-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-129">FocusStates</span></span>|<span data-ttu-id="5dfd6-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-130">The control does not have focus.</span></span>|
|<span data-ttu-id="5dfd6-131">Помечено</span><span class="sxs-lookup"><span data-stu-id="5dfd6-131">Checked</span></span>|<span data-ttu-id="5dfd6-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-132">CheckStates</span></span>|<span data-ttu-id="5dfd6-133">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="5dfd6-134">Unchecked</span><span class="sxs-lookup"><span data-stu-id="5dfd6-134">Unchecked</span></span>|<span data-ttu-id="5dfd6-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-135">CheckStates</span></span>|<span data-ttu-id="5dfd6-136">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="5dfd6-137">Неопределенное</span><span class="sxs-lookup"><span data-stu-id="5dfd6-137">Indeterminate</span></span>|<span data-ttu-id="5dfd6-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-138">CheckStates</span></span>|<span data-ttu-id="5dfd6-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> — `true`, и <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> является `null`.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="5dfd6-140">Valid</span><span class="sxs-lookup"><span data-stu-id="5dfd6-140">Valid</span></span>|<span data-ttu-id="5dfd6-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-141">ValidationStates</span></span>|<span data-ttu-id="5dfd6-142">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="5dfd6-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5dfd6-143">InvalidFocused</span></span>|<span data-ttu-id="5dfd6-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-144">ValidationStates</span></span>|<span data-ttu-id="5dfd6-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="5dfd6-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5dfd6-146">InvalidUnfocused</span></span>|<span data-ttu-id="5dfd6-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5dfd6-147">ValidationStates</span></span>|<span data-ttu-id="5dfd6-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="5dfd6-149">Если не определен визуальное состояние не существует в шаблоне элемента управления, Unchecked визуальное состояние будет использоваться как визуальное состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="5dfd6-150">Пример шаблона элемента управления ToggleButton</span><span class="sxs-lookup"><span data-stu-id="5dfd6-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="5dfd6-151">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="5dfd6-152">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5dfd6-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="5dfd6-153">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5dfd6-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dfd6-154">См. также</span><span class="sxs-lookup"><span data-stu-id="5dfd6-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5dfd6-155">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="5dfd6-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5dfd6-156">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="5dfd6-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5dfd6-157">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="5dfd6-157">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="5dfd6-158">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5dfd6-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
