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
ms.openlocfilehash: e987932e00be09fdf5ac34bb2bfb24a890368a15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596388"
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="b2fae-102">Стили и шаблоны элемента Thumb</span><span class="sxs-lookup"><span data-stu-id="b2fae-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="b2fae-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b2fae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="b2fae-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b2fae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b2fae-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b2fae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="b2fae-106">Бегунок частей</span><span class="sxs-lookup"><span data-stu-id="b2fae-106">Thumb Parts</span></span>  
 <span data-ttu-id="b2fae-107"><xref:System.Windows.Controls.Primitives.Thumb> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="b2fae-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="b2fae-108">Бегунок состояний</span><span class="sxs-lookup"><span data-stu-id="b2fae-108">Thumb States</span></span>  
 <span data-ttu-id="b2fae-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b2fae-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="b2fae-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="b2fae-110">VisualState Name</span></span>|<span data-ttu-id="b2fae-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b2fae-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b2fae-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="b2fae-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b2fae-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="b2fae-113">Normal</span></span>|<span data-ttu-id="b2fae-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-114">CommonStates</span></span>|<span data-ttu-id="b2fae-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2fae-115">The default state.</span></span>|  
|<span data-ttu-id="b2fae-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b2fae-116">MouseOver</span></span>|<span data-ttu-id="b2fae-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-117">CommonStates</span></span>|<span data-ttu-id="b2fae-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b2fae-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b2fae-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="b2fae-119">Pressed</span></span>|<span data-ttu-id="b2fae-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-120">CommonStates</span></span>|<span data-ttu-id="b2fae-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="b2fae-121">The control is pressed.</span></span>|  
|<span data-ttu-id="b2fae-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="b2fae-122">Disabled</span></span>|<span data-ttu-id="b2fae-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-123">CommonStates</span></span>|<span data-ttu-id="b2fae-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="b2fae-124">The control is disabled.</span></span>|  
|<span data-ttu-id="b2fae-125">Focused</span><span class="sxs-lookup"><span data-stu-id="b2fae-125">Focused</span></span>|<span data-ttu-id="b2fae-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-126">FocusStates</span></span>|<span data-ttu-id="b2fae-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b2fae-127">The control has focus.</span></span>|  
|<span data-ttu-id="b2fae-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="b2fae-128">Unfocused</span></span>|<span data-ttu-id="b2fae-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-129">FocusStates</span></span>|<span data-ttu-id="b2fae-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b2fae-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="b2fae-131">Valid</span><span class="sxs-lookup"><span data-stu-id="b2fae-131">Valid</span></span>|<span data-ttu-id="b2fae-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-132">ValidationStates</span></span>|<span data-ttu-id="b2fae-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="b2fae-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b2fae-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b2fae-134">InvalidFocused</span></span>|<span data-ttu-id="b2fae-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-135">ValidationStates</span></span>|<span data-ttu-id="b2fae-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b2fae-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b2fae-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b2fae-137">InvalidUnfocused</span></span>|<span data-ttu-id="b2fae-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2fae-138">ValidationStates</span></span>|<span data-ttu-id="b2fae-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="b2fae-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="b2fae-140">Пример шаблона элемента управления Thumb</span><span class="sxs-lookup"><span data-stu-id="b2fae-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="b2fae-141">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b2fae-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="b2fae-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b2fae-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b2fae-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b2fae-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fae-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b2fae-144">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b2fae-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="b2fae-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="b2fae-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="b2fae-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="b2fae-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="b2fae-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="b2fae-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b2fae-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
