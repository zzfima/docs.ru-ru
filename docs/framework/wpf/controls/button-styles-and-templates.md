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
ms.openlocfilehash: 854160e8b1b049fdb2f3421b9eb24cf410f33672
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457168"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="8b57a-102">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="8b57a-102">Button Styles and Templates</span></span>
<span data-ttu-id="8b57a-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8b57a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="8b57a-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8b57a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8b57a-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8b57a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="8b57a-106">Кнопка частей</span><span class="sxs-lookup"><span data-stu-id="8b57a-106">Button Parts</span></span>  
 <span data-ttu-id="8b57a-107"><xref:System.Windows.Controls.Button> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="8b57a-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="8b57a-108">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="8b57a-108">Button States</span></span>  
 <span data-ttu-id="8b57a-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8b57a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="8b57a-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="8b57a-110">VisualState Name</span></span>|<span data-ttu-id="8b57a-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8b57a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8b57a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8b57a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8b57a-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="8b57a-113">Normal</span></span>|<span data-ttu-id="8b57a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-114">CommonStates</span></span>|<span data-ttu-id="8b57a-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b57a-115">The default state.</span></span>|  
|<span data-ttu-id="8b57a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8b57a-116">MouseOver</span></span>|<span data-ttu-id="8b57a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-117">CommonStates</span></span>|<span data-ttu-id="8b57a-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="8b57a-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="8b57a-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="8b57a-119">Pressed</span></span>|<span data-ttu-id="8b57a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-120">CommonStates</span></span>|<span data-ttu-id="8b57a-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="8b57a-121">The control is pressed.</span></span>|  
|<span data-ttu-id="8b57a-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="8b57a-122">Disabled</span></span>|<span data-ttu-id="8b57a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-123">CommonStates</span></span>|<span data-ttu-id="8b57a-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="8b57a-124">The control is disabled.</span></span>|  
|<span data-ttu-id="8b57a-125">Focused</span><span class="sxs-lookup"><span data-stu-id="8b57a-125">Focused</span></span>|<span data-ttu-id="8b57a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-126">FocusStates</span></span>|<span data-ttu-id="8b57a-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="8b57a-127">The control has focus.</span></span>|  
|<span data-ttu-id="8b57a-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="8b57a-128">Unfocused</span></span>|<span data-ttu-id="8b57a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-129">FocusStates</span></span>|<span data-ttu-id="8b57a-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="8b57a-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="8b57a-131">Valid</span><span class="sxs-lookup"><span data-stu-id="8b57a-131">Valid</span></span>|<span data-ttu-id="8b57a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-132">ValidationStates</span></span>|<span data-ttu-id="8b57a-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="8b57a-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8b57a-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8b57a-134">InvalidFocused</span></span>|<span data-ttu-id="8b57a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-135">ValidationStates</span></span>|<span data-ttu-id="8b57a-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` и элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="8b57a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="8b57a-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8b57a-137">InvalidUnfocused</span></span>|<span data-ttu-id="8b57a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8b57a-138">ValidationStates</span></span>|<span data-ttu-id="8b57a-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` и элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="8b57a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="8b57a-140">Пример шаблона элемента управления кнопки</span><span class="sxs-lookup"><span data-stu-id="8b57a-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="8b57a-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8b57a-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="8b57a-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8b57a-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8b57a-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8b57a-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b57a-144">См. также</span><span class="sxs-lookup"><span data-stu-id="8b57a-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="8b57a-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="8b57a-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="8b57a-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="8b57a-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="8b57a-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="8b57a-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="8b57a-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8b57a-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
