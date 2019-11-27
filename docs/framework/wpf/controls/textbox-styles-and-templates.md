---
title: Стили и шаблоны элемента TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 41e390c261836909240cc146a48729d48c4a410e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283704"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="b168f-102">Стили и шаблоны элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="b168f-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="b168f-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b168f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="b168f-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b168f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b168f-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="b168f-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="b168f-106">Части текстового поля</span><span class="sxs-lookup"><span data-stu-id="b168f-106">TextBox Parts</span></span>  
 <span data-ttu-id="b168f-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b168f-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="b168f-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="b168f-108">Part</span></span>|<span data-ttu-id="b168f-109">Введите</span><span class="sxs-lookup"><span data-stu-id="b168f-109">Type</span></span>|<span data-ttu-id="b168f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b168f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b168f-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="b168f-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="b168f-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="b168f-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b168f-113">Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="b168f-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="b168f-114">Состояния текстового поля</span><span class="sxs-lookup"><span data-stu-id="b168f-114">TextBox States</span></span>  
 <span data-ttu-id="b168f-115">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b168f-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="b168f-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="b168f-116">VisualState Name</span></span>|<span data-ttu-id="b168f-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b168f-117">VisualStateGroup Name</span></span>|<span data-ttu-id="b168f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b168f-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="b168f-119">Нормальный</span><span class="sxs-lookup"><span data-stu-id="b168f-119">Normal</span></span>|<span data-ttu-id="b168f-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b168f-120">CommonStates</span></span>|<span data-ttu-id="b168f-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b168f-121">The default state.</span></span>|  
|<span data-ttu-id="b168f-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b168f-122">MouseOver</span></span>|<span data-ttu-id="b168f-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b168f-123">CommonStates</span></span>|<span data-ttu-id="b168f-124">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b168f-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b168f-125">Отключено.</span><span class="sxs-lookup"><span data-stu-id="b168f-125">Disabled</span></span>|<span data-ttu-id="b168f-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b168f-126">CommonStates</span></span>|<span data-ttu-id="b168f-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="b168f-127">The control is disabled.</span></span>|  
|<span data-ttu-id="b168f-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b168f-128">ReadOnly</span></span>|<span data-ttu-id="b168f-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b168f-129">CommonStates</span></span>|<span data-ttu-id="b168f-130">Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b168f-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="b168f-131">Focused</span><span class="sxs-lookup"><span data-stu-id="b168f-131">Focused</span></span>|<span data-ttu-id="b168f-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b168f-132">FocusStates</span></span>|<span data-ttu-id="b168f-133">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b168f-133">The control has focus.</span></span>|  
|<span data-ttu-id="b168f-134">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="b168f-134">Unfocused</span></span>|<span data-ttu-id="b168f-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b168f-135">FocusStates</span></span>|<span data-ttu-id="b168f-136">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b168f-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="b168f-137">Valid</span><span class="sxs-lookup"><span data-stu-id="b168f-137">Valid</span></span>|<span data-ttu-id="b168f-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b168f-138">ValidationStates</span></span>|<span data-ttu-id="b168f-139">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="b168f-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b168f-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b168f-140">InvalidFocused</span></span>|<span data-ttu-id="b168f-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b168f-141">ValidationStates</span></span>|<span data-ttu-id="b168f-142">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b168f-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b168f-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b168f-143">InvalidUnfocused</span></span>|<span data-ttu-id="b168f-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b168f-144">ValidationStates</span></span>|<span data-ttu-id="b168f-145">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b168f-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="b168f-146">Пример ControlTemplate для TextBox</span><span class="sxs-lookup"><span data-stu-id="b168f-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="b168f-147">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b168f-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="b168f-148">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b168f-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b168f-149">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b168f-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b168f-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b168f-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b168f-151">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="b168f-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b168f-152">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="b168f-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b168f-153">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="b168f-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b168f-154">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="b168f-154">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
