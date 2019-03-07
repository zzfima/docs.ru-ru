---
title: RepeatButton стили и шаблоны
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509593"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="6ed1c-102">RepeatButton стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="6ed1c-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="6ed1c-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="6ed1c-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6ed1c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6ed1c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="6ed1c-106">RepeatButton частей</span><span class="sxs-lookup"><span data-stu-id="6ed1c-106">RepeatButton Parts</span></span>

<span data-ttu-id="6ed1c-107"><xref:System.Windows.Controls.Primitives.RepeatButton> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="6ed1c-108">RepeatButton состояний</span><span class="sxs-lookup"><span data-stu-id="6ed1c-108">RepeatButton States</span></span>

<span data-ttu-id="6ed1c-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="6ed1c-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="6ed1c-110">VisualState Name</span></span>|<span data-ttu-id="6ed1c-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6ed1c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6ed1c-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="6ed1c-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6ed1c-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-113">Normal</span></span>|<span data-ttu-id="6ed1c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-114">CommonStates</span></span>|<span data-ttu-id="6ed1c-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-115">The default state.</span></span>|
|<span data-ttu-id="6ed1c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6ed1c-116">MouseOver</span></span>|<span data-ttu-id="6ed1c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-117">CommonStates</span></span>|<span data-ttu-id="6ed1c-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="6ed1c-119">Pressed</span><span class="sxs-lookup"><span data-stu-id="6ed1c-119">Pressed</span></span>|<span data-ttu-id="6ed1c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-120">CommonStates</span></span>|<span data-ttu-id="6ed1c-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-121">The control is pressed.</span></span>|
|<span data-ttu-id="6ed1c-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="6ed1c-122">Disabled</span></span>|<span data-ttu-id="6ed1c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-123">CommonStates</span></span>|<span data-ttu-id="6ed1c-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-124">The control is disabled.</span></span>|
|<span data-ttu-id="6ed1c-125">Focused</span><span class="sxs-lookup"><span data-stu-id="6ed1c-125">Focused</span></span>|<span data-ttu-id="6ed1c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-126">FocusStates</span></span>|<span data-ttu-id="6ed1c-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-127">The control has focus.</span></span>|
|<span data-ttu-id="6ed1c-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="6ed1c-128">Unfocused</span></span>|<span data-ttu-id="6ed1c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-129">FocusStates</span></span>|<span data-ttu-id="6ed1c-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-130">The control does not have focus.</span></span>|
|<span data-ttu-id="6ed1c-131">Допустимый</span><span class="sxs-lookup"><span data-stu-id="6ed1c-131">Valid</span></span>|<span data-ttu-id="6ed1c-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-132">ValidationStates</span></span>|<span data-ttu-id="6ed1c-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="6ed1c-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6ed1c-134">InvalidFocused</span></span>|<span data-ttu-id="6ed1c-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-135">ValidationStates</span></span>|<span data-ttu-id="6ed1c-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="6ed1c-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6ed1c-137">InvalidUnfocused</span></span>|<span data-ttu-id="6ed1c-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6ed1c-138">ValidationStates</span></span>|<span data-ttu-id="6ed1c-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="6ed1c-140">Пример шаблона элемента управления RepeatButton</span><span class="sxs-lookup"><span data-stu-id="6ed1c-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="6ed1c-141">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="6ed1c-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6ed1c-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="6ed1c-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="6ed1c-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ed1c-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6ed1c-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6ed1c-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="6ed1c-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6ed1c-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="6ed1c-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6ed1c-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="6ed1c-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="6ed1c-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6ed1c-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
