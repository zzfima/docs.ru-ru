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
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283463"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="afcf5-102">Стили и шаблоны элемента PasswordBox</span><span class="sxs-lookup"><span data-stu-id="afcf5-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="afcf5-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="afcf5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="afcf5-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="afcf5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="afcf5-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="afcf5-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="afcf5-106">PasswordBox части</span><span class="sxs-lookup"><span data-stu-id="afcf5-106">PasswordBox Parts</span></span>

<span data-ttu-id="afcf5-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="afcf5-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="afcf5-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="afcf5-108">Part</span></span>|<span data-ttu-id="afcf5-109">Тип</span><span class="sxs-lookup"><span data-stu-id="afcf5-109">Type</span></span>|<span data-ttu-id="afcf5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="afcf5-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="afcf5-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="afcf5-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="afcf5-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="afcf5-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="afcf5-113">Текст <xref:System.Windows.Controls.PasswordBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="afcf5-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="afcf5-114">Состояния PasswordBox</span><span class="sxs-lookup"><span data-stu-id="afcf5-114">PasswordBox States</span></span>

<span data-ttu-id="afcf5-115">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="afcf5-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="afcf5-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="afcf5-116">VisualState Name</span></span>|<span data-ttu-id="afcf5-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="afcf5-117">VisualStateGroup Name</span></span>|<span data-ttu-id="afcf5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="afcf5-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="afcf5-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="afcf5-119">Normal</span></span>|<span data-ttu-id="afcf5-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-120">CommonStates</span></span>|<span data-ttu-id="afcf5-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afcf5-121">The default state.</span></span>|
|<span data-ttu-id="afcf5-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="afcf5-122">MouseOver</span></span>|<span data-ttu-id="afcf5-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-123">CommonStates</span></span>|<span data-ttu-id="afcf5-124">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="afcf5-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="afcf5-125">Отключено.</span><span class="sxs-lookup"><span data-stu-id="afcf5-125">Disabled</span></span>|<span data-ttu-id="afcf5-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-126">CommonStates</span></span>|<span data-ttu-id="afcf5-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="afcf5-127">The control is disabled.</span></span>|
|<span data-ttu-id="afcf5-128">Focused</span><span class="sxs-lookup"><span data-stu-id="afcf5-128">Focused</span></span>|<span data-ttu-id="afcf5-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-129">FocusStates</span></span>|<span data-ttu-id="afcf5-130">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="afcf5-130">The control has focus.</span></span>|
|<span data-ttu-id="afcf5-131">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="afcf5-131">Unfocused</span></span>|<span data-ttu-id="afcf5-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-132">FocusStates</span></span>|<span data-ttu-id="afcf5-133">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="afcf5-133">The control does not have focus.</span></span>|
|<span data-ttu-id="afcf5-134">Valid</span><span class="sxs-lookup"><span data-stu-id="afcf5-134">Valid</span></span>|<span data-ttu-id="afcf5-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-135">ValidationStates</span></span>|<span data-ttu-id="afcf5-136">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="afcf5-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="afcf5-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="afcf5-137">InvalidFocused</span></span>|<span data-ttu-id="afcf5-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-138">ValidationStates</span></span>|<span data-ttu-id="afcf5-139">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="afcf5-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="afcf5-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="afcf5-140">InvalidUnfocused</span></span>|<span data-ttu-id="afcf5-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afcf5-141">ValidationStates</span></span>|<span data-ttu-id="afcf5-142">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="afcf5-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="afcf5-143">Пример ControlTemplate PasswordBox</span><span class="sxs-lookup"><span data-stu-id="afcf5-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="afcf5-144">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="afcf5-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="afcf5-145">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="afcf5-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="afcf5-146">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="afcf5-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="afcf5-147">См. также</span><span class="sxs-lookup"><span data-stu-id="afcf5-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="afcf5-148">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="afcf5-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="afcf5-149">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="afcf5-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="afcf5-150">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="afcf5-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="afcf5-151">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="afcf5-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
