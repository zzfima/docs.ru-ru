---
title: Стили и шаблоны элемента PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 227ccbda8d570868258508935a5d95f0f40663ab
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458835"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="6b53c-102">Стили и шаблоны элемента PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b53c-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="6b53c-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="6b53c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="6b53c-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6b53c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6b53c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6b53c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="6b53c-106">PasswordBox части</span><span class="sxs-lookup"><span data-stu-id="6b53c-106">PasswordBox Parts</span></span>

<span data-ttu-id="6b53c-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="6b53c-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="6b53c-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="6b53c-108">Part</span></span>|<span data-ttu-id="6b53c-109">Type</span><span class="sxs-lookup"><span data-stu-id="6b53c-109">Type</span></span>|<span data-ttu-id="6b53c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6b53c-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6b53c-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="6b53c-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="6b53c-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="6b53c-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="6b53c-113">Текст <xref:System.Windows.Controls.PasswordBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="6b53c-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="6b53c-114">Состояния PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b53c-114">PasswordBox States</span></span>

<span data-ttu-id="6b53c-115">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="6b53c-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="6b53c-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="6b53c-116">VisualState Name</span></span>|<span data-ttu-id="6b53c-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6b53c-117">VisualStateGroup Name</span></span>|<span data-ttu-id="6b53c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6b53c-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6b53c-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="6b53c-119">Normal</span></span>|<span data-ttu-id="6b53c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-120">CommonStates</span></span>|<span data-ttu-id="6b53c-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b53c-121">The default state.</span></span>|
|<span data-ttu-id="6b53c-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6b53c-122">MouseOver</span></span>|<span data-ttu-id="6b53c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-123">CommonStates</span></span>|<span data-ttu-id="6b53c-124">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6b53c-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="6b53c-125">Отключено.</span><span class="sxs-lookup"><span data-stu-id="6b53c-125">Disabled</span></span>|<span data-ttu-id="6b53c-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-126">CommonStates</span></span>|<span data-ttu-id="6b53c-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="6b53c-127">The control is disabled.</span></span>|
|<span data-ttu-id="6b53c-128">Focused</span><span class="sxs-lookup"><span data-stu-id="6b53c-128">Focused</span></span>|<span data-ttu-id="6b53c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-129">FocusStates</span></span>|<span data-ttu-id="6b53c-130">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6b53c-130">The control has focus.</span></span>|
|<span data-ttu-id="6b53c-131">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="6b53c-131">Unfocused</span></span>|<span data-ttu-id="6b53c-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-132">FocusStates</span></span>|<span data-ttu-id="6b53c-133">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6b53c-133">The control does not have focus.</span></span>|
|<span data-ttu-id="6b53c-134">Valid</span><span class="sxs-lookup"><span data-stu-id="6b53c-134">Valid</span></span>|<span data-ttu-id="6b53c-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-135">ValidationStates</span></span>|<span data-ttu-id="6b53c-136">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="6b53c-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="6b53c-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6b53c-137">InvalidFocused</span></span>|<span data-ttu-id="6b53c-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-138">ValidationStates</span></span>|<span data-ttu-id="6b53c-139">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6b53c-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="6b53c-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6b53c-140">InvalidUnfocused</span></span>|<span data-ttu-id="6b53c-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6b53c-141">ValidationStates</span></span>|<span data-ttu-id="6b53c-142">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6b53c-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="6b53c-143">Пример ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6b53c-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="6b53c-144">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="6b53c-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="6b53c-145">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6b53c-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="6b53c-146">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="6b53c-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b53c-147">См. также</span><span class="sxs-lookup"><span data-stu-id="6b53c-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6b53c-148">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="6b53c-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6b53c-149">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="6b53c-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6b53c-150">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="6b53c-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="6b53c-151">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6b53c-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
