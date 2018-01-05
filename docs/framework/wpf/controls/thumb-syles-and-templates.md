---
title: "Стили и шаблоны элемента Thumb"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 780ddc07c79aab111c17f9e7e551cfde85c68f3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="75afa-102">Стили и шаблоны элемента Thumb</span><span class="sxs-lookup"><span data-stu-id="75afa-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="75afa-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="75afa-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="75afa-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="75afa-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="75afa-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="75afa-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="75afa-106">Бегунок частей</span><span class="sxs-lookup"><span data-stu-id="75afa-106">Thumb Parts</span></span>  
 <span data-ttu-id="75afa-107"><xref:System.Windows.Controls.Primitives.Thumb> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="75afa-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="75afa-108">Бегунок состояний</span><span class="sxs-lookup"><span data-stu-id="75afa-108">Thumb States</span></span>  
 <span data-ttu-id="75afa-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="75afa-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="75afa-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="75afa-110">VisualState Name</span></span>|<span data-ttu-id="75afa-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="75afa-111">VisualStateGroup Name</span></span>|<span data-ttu-id="75afa-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="75afa-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="75afa-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="75afa-113">Normal</span></span>|<span data-ttu-id="75afa-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75afa-114">CommonStates</span></span>|<span data-ttu-id="75afa-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75afa-115">The default state.</span></span>|  
|<span data-ttu-id="75afa-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="75afa-116">MouseOver</span></span>|<span data-ttu-id="75afa-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75afa-117">CommonStates</span></span>|<span data-ttu-id="75afa-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="75afa-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="75afa-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="75afa-119">Pressed</span></span>|<span data-ttu-id="75afa-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75afa-120">CommonStates</span></span>|<span data-ttu-id="75afa-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="75afa-121">The control is pressed.</span></span>|  
|<span data-ttu-id="75afa-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="75afa-122">Disabled</span></span>|<span data-ttu-id="75afa-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="75afa-123">CommonStates</span></span>|<span data-ttu-id="75afa-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="75afa-124">The control is disabled.</span></span>|  
|<span data-ttu-id="75afa-125">Focused</span><span class="sxs-lookup"><span data-stu-id="75afa-125">Focused</span></span>|<span data-ttu-id="75afa-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="75afa-126">FocusStates</span></span>|<span data-ttu-id="75afa-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="75afa-127">The control has focus.</span></span>|  
|<span data-ttu-id="75afa-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="75afa-128">Unfocused</span></span>|<span data-ttu-id="75afa-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="75afa-129">FocusStates</span></span>|<span data-ttu-id="75afa-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="75afa-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="75afa-131">Valid</span><span class="sxs-lookup"><span data-stu-id="75afa-131">Valid</span></span>|<span data-ttu-id="75afa-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75afa-132">ValidationStates</span></span>|<span data-ttu-id="75afa-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="75afa-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="75afa-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="75afa-134">InvalidFocused</span></span>|<span data-ttu-id="75afa-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75afa-135">ValidationStates</span></span>|<span data-ttu-id="75afa-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="75afa-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="75afa-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="75afa-137">InvalidUnfocused</span></span>|<span data-ttu-id="75afa-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="75afa-138">ValidationStates</span></span>|<span data-ttu-id="75afa-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="75afa-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="75afa-140">Пример шаблона элемента управления "бегунок"</span><span class="sxs-lookup"><span data-stu-id="75afa-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="75afa-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="75afa-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="75afa-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="75afa-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="75afa-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="75afa-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75afa-144">См. также</span><span class="sxs-lookup"><span data-stu-id="75afa-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="75afa-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="75afa-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="75afa-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="75afa-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="75afa-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="75afa-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="75afa-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="75afa-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
