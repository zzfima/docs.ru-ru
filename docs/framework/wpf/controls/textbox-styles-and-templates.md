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
ms.openlocfilehash: 7c4680a3ea9352e94d628e786fc8e4fd71018d00
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458250"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="a4769-102">Стили и шаблоны элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="a4769-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="a4769-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4769-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="a4769-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a4769-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a4769-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a4769-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="a4769-106">Части текстового поля</span><span class="sxs-lookup"><span data-stu-id="a4769-106">TextBox Parts</span></span>  
 <span data-ttu-id="a4769-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4769-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="a4769-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="a4769-108">Part</span></span>|<span data-ttu-id="a4769-109">Type</span><span class="sxs-lookup"><span data-stu-id="a4769-109">Type</span></span>|<span data-ttu-id="a4769-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a4769-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4769-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="a4769-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a4769-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="a4769-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="a4769-113">Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="a4769-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="a4769-114">Состояния текстового поля</span><span class="sxs-lookup"><span data-stu-id="a4769-114">TextBox States</span></span>  
 <span data-ttu-id="a4769-115">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4769-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="a4769-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="a4769-116">VisualState Name</span></span>|<span data-ttu-id="a4769-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a4769-117">VisualStateGroup Name</span></span>|<span data-ttu-id="a4769-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a4769-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a4769-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="a4769-119">Normal</span></span>|<span data-ttu-id="a4769-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4769-120">CommonStates</span></span>|<span data-ttu-id="a4769-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4769-121">The default state.</span></span>|  
|<span data-ttu-id="a4769-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a4769-122">MouseOver</span></span>|<span data-ttu-id="a4769-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4769-123">CommonStates</span></span>|<span data-ttu-id="a4769-124">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="a4769-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a4769-125">Отключено.</span><span class="sxs-lookup"><span data-stu-id="a4769-125">Disabled</span></span>|<span data-ttu-id="a4769-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4769-126">CommonStates</span></span>|<span data-ttu-id="a4769-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="a4769-127">The control is disabled.</span></span>|  
|<span data-ttu-id="a4769-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a4769-128">ReadOnly</span></span>|<span data-ttu-id="a4769-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4769-129">CommonStates</span></span>|<span data-ttu-id="a4769-130">Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4769-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="a4769-131">Focused</span><span class="sxs-lookup"><span data-stu-id="a4769-131">Focused</span></span>|<span data-ttu-id="a4769-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a4769-132">FocusStates</span></span>|<span data-ttu-id="a4769-133">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a4769-133">The control has focus.</span></span>|  
|<span data-ttu-id="a4769-134">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="a4769-134">Unfocused</span></span>|<span data-ttu-id="a4769-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a4769-135">FocusStates</span></span>|<span data-ttu-id="a4769-136">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="a4769-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="a4769-137">Valid</span><span class="sxs-lookup"><span data-stu-id="a4769-137">Valid</span></span>|<span data-ttu-id="a4769-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4769-138">ValidationStates</span></span>|<span data-ttu-id="a4769-139">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="a4769-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a4769-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a4769-140">InvalidFocused</span></span>|<span data-ttu-id="a4769-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4769-141">ValidationStates</span></span>|<span data-ttu-id="a4769-142">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a4769-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a4769-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a4769-143">InvalidUnfocused</span></span>|<span data-ttu-id="a4769-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4769-144">ValidationStates</span></span>|<span data-ttu-id="a4769-145">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="a4769-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="a4769-146">Пример ControlTemplate для TextBox</span><span class="sxs-lookup"><span data-stu-id="a4769-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="a4769-147">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4769-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="a4769-148">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a4769-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a4769-149">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a4769-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4769-150">См. также</span><span class="sxs-lookup"><span data-stu-id="a4769-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a4769-151">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="a4769-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a4769-152">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="a4769-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a4769-153">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="a4769-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a4769-154">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a4769-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
