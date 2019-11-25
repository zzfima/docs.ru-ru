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
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283579"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="5bc65-102">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="5bc65-102">Button Styles and Templates</span></span>
<span data-ttu-id="5bc65-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5bc65-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="5bc65-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bc65-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5bc65-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="5bc65-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="5bc65-106">Части кнопки</span><span class="sxs-lookup"><span data-stu-id="5bc65-106">Button Parts</span></span>  
 <span data-ttu-id="5bc65-107">Элемент управления <xref:System.Windows.Controls.Button> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="5bc65-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="5bc65-108">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="5bc65-108">Button States</span></span>  
 <span data-ttu-id="5bc65-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5bc65-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="5bc65-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="5bc65-110">VisualState Name</span></span>|<span data-ttu-id="5bc65-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5bc65-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5bc65-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5bc65-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5bc65-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="5bc65-113">Normal</span></span>|<span data-ttu-id="5bc65-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-114">CommonStates</span></span>|<span data-ttu-id="5bc65-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5bc65-115">The default state.</span></span>|  
|<span data-ttu-id="5bc65-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5bc65-116">MouseOver</span></span>|<span data-ttu-id="5bc65-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-117">CommonStates</span></span>|<span data-ttu-id="5bc65-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="5bc65-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="5bc65-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="5bc65-119">Pressed</span></span>|<span data-ttu-id="5bc65-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-120">CommonStates</span></span>|<span data-ttu-id="5bc65-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="5bc65-121">The control is pressed.</span></span>|  
|<span data-ttu-id="5bc65-122">Отключено.</span><span class="sxs-lookup"><span data-stu-id="5bc65-122">Disabled</span></span>|<span data-ttu-id="5bc65-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-123">CommonStates</span></span>|<span data-ttu-id="5bc65-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="5bc65-124">The control is disabled.</span></span>|  
|<span data-ttu-id="5bc65-125">Focused</span><span class="sxs-lookup"><span data-stu-id="5bc65-125">Focused</span></span>|<span data-ttu-id="5bc65-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-126">FocusStates</span></span>|<span data-ttu-id="5bc65-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5bc65-127">The control has focus.</span></span>|  
|<span data-ttu-id="5bc65-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="5bc65-128">Unfocused</span></span>|<span data-ttu-id="5bc65-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-129">FocusStates</span></span>|<span data-ttu-id="5bc65-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5bc65-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="5bc65-131">Valid</span><span class="sxs-lookup"><span data-stu-id="5bc65-131">Valid</span></span>|<span data-ttu-id="5bc65-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-132">ValidationStates</span></span>|<span data-ttu-id="5bc65-133">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="5bc65-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5bc65-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5bc65-134">InvalidFocused</span></span>|<span data-ttu-id="5bc65-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-135">ValidationStates</span></span>|<span data-ttu-id="5bc65-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5bc65-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="5bc65-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5bc65-137">InvalidUnfocused</span></span>|<span data-ttu-id="5bc65-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bc65-138">ValidationStates</span></span>|<span data-ttu-id="5bc65-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5bc65-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="5bc65-140">Пример ControlTemplate для кнопки</span><span class="sxs-lookup"><span data-stu-id="5bc65-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="5bc65-141">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5bc65-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="5bc65-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5bc65-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5bc65-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5bc65-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc65-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5bc65-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5bc65-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="5bc65-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5bc65-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="5bc65-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5bc65-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="5bc65-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5bc65-148">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="5bc65-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
