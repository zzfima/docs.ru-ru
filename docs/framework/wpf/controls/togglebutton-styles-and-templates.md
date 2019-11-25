---
title: Стили и шаблоны элемента ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: a4c449a561017659db7f54fd3cdb8964742650de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283676"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="459a0-102">Стили и шаблоны элемента ToggleButton</span><span class="sxs-lookup"><span data-stu-id="459a0-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="459a0-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="459a0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="459a0-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="459a0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="459a0-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="459a0-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="459a0-106">Компоненты ToggleButton</span><span class="sxs-lookup"><span data-stu-id="459a0-106">ToggleButton Parts</span></span>

<span data-ttu-id="459a0-107">Элемент управления <xref:System.Windows.Controls.Primitives.ToggleButton> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="459a0-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="459a0-108">Состояния ToggleButton</span><span class="sxs-lookup"><span data-stu-id="459a0-108">ToggleButton States</span></span>

<span data-ttu-id="459a0-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="459a0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="459a0-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="459a0-110">VisualState Name</span></span>|<span data-ttu-id="459a0-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="459a0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="459a0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="459a0-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="459a0-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="459a0-113">Normal</span></span>|<span data-ttu-id="459a0-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="459a0-114">CommonStates</span></span>|<span data-ttu-id="459a0-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="459a0-115">The default state.</span></span>|
|<span data-ttu-id="459a0-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="459a0-116">MouseOver</span></span>|<span data-ttu-id="459a0-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="459a0-117">CommonStates</span></span>|<span data-ttu-id="459a0-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="459a0-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="459a0-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="459a0-119">Pressed</span></span>|<span data-ttu-id="459a0-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="459a0-120">CommonStates</span></span>|<span data-ttu-id="459a0-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="459a0-121">The control is pressed.</span></span>|
|<span data-ttu-id="459a0-122">Отключено.</span><span class="sxs-lookup"><span data-stu-id="459a0-122">Disabled</span></span>|<span data-ttu-id="459a0-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="459a0-123">CommonStates</span></span>|<span data-ttu-id="459a0-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="459a0-124">The control is disabled.</span></span>|
|<span data-ttu-id="459a0-125">Focused</span><span class="sxs-lookup"><span data-stu-id="459a0-125">Focused</span></span>|<span data-ttu-id="459a0-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="459a0-126">FocusStates</span></span>|<span data-ttu-id="459a0-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="459a0-127">The control has focus.</span></span>|
|<span data-ttu-id="459a0-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="459a0-128">Unfocused</span></span>|<span data-ttu-id="459a0-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="459a0-129">FocusStates</span></span>|<span data-ttu-id="459a0-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="459a0-130">The control does not have focus.</span></span>|
|<span data-ttu-id="459a0-131">Помечено</span><span class="sxs-lookup"><span data-stu-id="459a0-131">Checked</span></span>|<span data-ttu-id="459a0-132">чеккстатес</span><span class="sxs-lookup"><span data-stu-id="459a0-132">CheckStates</span></span>|<span data-ttu-id="459a0-133">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="459a0-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="459a0-134">Unchecked</span><span class="sxs-lookup"><span data-stu-id="459a0-134">Unchecked</span></span>|<span data-ttu-id="459a0-135">чеккстатес</span><span class="sxs-lookup"><span data-stu-id="459a0-135">CheckStates</span></span>|<span data-ttu-id="459a0-136">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="459a0-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="459a0-137">Неопределенному</span><span class="sxs-lookup"><span data-stu-id="459a0-137">Indeterminate</span></span>|<span data-ttu-id="459a0-138">чеккстатес</span><span class="sxs-lookup"><span data-stu-id="459a0-138">CheckStates</span></span>|<span data-ttu-id="459a0-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> `true`, а <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> — `null`.</span><span class="sxs-lookup"><span data-stu-id="459a0-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="459a0-140">Valid</span><span class="sxs-lookup"><span data-stu-id="459a0-140">Valid</span></span>|<span data-ttu-id="459a0-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="459a0-141">ValidationStates</span></span>|<span data-ttu-id="459a0-142">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="459a0-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="459a0-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="459a0-143">InvalidFocused</span></span>|<span data-ttu-id="459a0-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="459a0-144">ValidationStates</span></span>|<span data-ttu-id="459a0-145">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="459a0-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="459a0-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="459a0-146">InvalidUnfocused</span></span>|<span data-ttu-id="459a0-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="459a0-147">ValidationStates</span></span>|<span data-ttu-id="459a0-148">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="459a0-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="459a0-149">Если неопределенное визуальное состояние не существует в шаблоне элемента управления, непроверенное визуальное состояние будет использоваться как визуальное состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="459a0-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="459a0-150">Пример объекта ControlTemplate для объекта ToggleButton</span><span class="sxs-lookup"><span data-stu-id="459a0-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="459a0-151">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="459a0-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="459a0-152">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="459a0-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="459a0-153">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="459a0-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="459a0-154">См. также</span><span class="sxs-lookup"><span data-stu-id="459a0-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="459a0-155">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="459a0-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="459a0-156">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="459a0-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="459a0-157">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="459a0-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="459a0-158">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="459a0-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
