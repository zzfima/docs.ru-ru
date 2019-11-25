---
title: Стили и шаблоны элемента RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 8585e98536fd908daa11f21da395cab44924d612
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283429"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="3179a-102">Стили и шаблоны элемента RepeatButton</span><span class="sxs-lookup"><span data-stu-id="3179a-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="3179a-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="3179a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="3179a-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3179a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3179a-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="3179a-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="3179a-106">Компоненты RepeatButton</span><span class="sxs-lookup"><span data-stu-id="3179a-106">RepeatButton Parts</span></span>

<span data-ttu-id="3179a-107">Элемент управления <xref:System.Windows.Controls.Primitives.RepeatButton> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="3179a-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="3179a-108">Состояния RepeatButton</span><span class="sxs-lookup"><span data-stu-id="3179a-108">RepeatButton States</span></span>

<span data-ttu-id="3179a-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="3179a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="3179a-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="3179a-110">VisualState Name</span></span>|<span data-ttu-id="3179a-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3179a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3179a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3179a-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="3179a-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="3179a-113">Normal</span></span>|<span data-ttu-id="3179a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3179a-114">CommonStates</span></span>|<span data-ttu-id="3179a-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3179a-115">The default state.</span></span>|
|<span data-ttu-id="3179a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3179a-116">MouseOver</span></span>|<span data-ttu-id="3179a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3179a-117">CommonStates</span></span>|<span data-ttu-id="3179a-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="3179a-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="3179a-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="3179a-119">Pressed</span></span>|<span data-ttu-id="3179a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3179a-120">CommonStates</span></span>|<span data-ttu-id="3179a-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="3179a-121">The control is pressed.</span></span>|
|<span data-ttu-id="3179a-122">Отключено.</span><span class="sxs-lookup"><span data-stu-id="3179a-122">Disabled</span></span>|<span data-ttu-id="3179a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3179a-123">CommonStates</span></span>|<span data-ttu-id="3179a-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="3179a-124">The control is disabled.</span></span>|
|<span data-ttu-id="3179a-125">Focused</span><span class="sxs-lookup"><span data-stu-id="3179a-125">Focused</span></span>|<span data-ttu-id="3179a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3179a-126">FocusStates</span></span>|<span data-ttu-id="3179a-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3179a-127">The control has focus.</span></span>|
|<span data-ttu-id="3179a-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="3179a-128">Unfocused</span></span>|<span data-ttu-id="3179a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3179a-129">FocusStates</span></span>|<span data-ttu-id="3179a-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="3179a-130">The control does not have focus.</span></span>|
|<span data-ttu-id="3179a-131">Valid</span><span class="sxs-lookup"><span data-stu-id="3179a-131">Valid</span></span>|<span data-ttu-id="3179a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3179a-132">ValidationStates</span></span>|<span data-ttu-id="3179a-133">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="3179a-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="3179a-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3179a-134">InvalidFocused</span></span>|<span data-ttu-id="3179a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3179a-135">ValidationStates</span></span>|<span data-ttu-id="3179a-136">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3179a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="3179a-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3179a-137">InvalidUnfocused</span></span>|<span data-ttu-id="3179a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3179a-138">ValidationStates</span></span>|<span data-ttu-id="3179a-139">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="3179a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="3179a-140">Пример объекта ControlTemplate для RepeatButton</span><span class="sxs-lookup"><span data-stu-id="3179a-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="3179a-141">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="3179a-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="3179a-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3179a-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="3179a-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3179a-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="3179a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="3179a-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3179a-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="3179a-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3179a-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="3179a-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3179a-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="3179a-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3179a-148">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="3179a-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
