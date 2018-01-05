---
title: "Стили и шаблоны элемента Expander"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 999b081d80680069d4c6fdf908814889afa60870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="dfb55-102">Стили и шаблоны элемента Expander</span><span class="sxs-lookup"><span data-stu-id="dfb55-102">Expander Styles and Templates</span></span>
<span data-ttu-id="dfb55-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Expander> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dfb55-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="dfb55-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dfb55-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="dfb55-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="dfb55-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="dfb55-106">Расширитель частей</span><span class="sxs-lookup"><span data-stu-id="dfb55-106">Expander Parts</span></span>  
 <span data-ttu-id="dfb55-107"><xref:System.Windows.Controls.Expander> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="dfb55-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="dfb55-108">Расширитель состояний</span><span class="sxs-lookup"><span data-stu-id="dfb55-108">Expander States</span></span>  
 <span data-ttu-id="dfb55-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Expander> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dfb55-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="dfb55-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="dfb55-110">VisualState Name</span></span>|<span data-ttu-id="dfb55-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="dfb55-111">VisualStateGroup Name</span></span>|<span data-ttu-id="dfb55-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="dfb55-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="dfb55-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="dfb55-113">Normal</span></span>|<span data-ttu-id="dfb55-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-114">CommonStates</span></span>|<span data-ttu-id="dfb55-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfb55-115">The default state.</span></span>|  
|<span data-ttu-id="dfb55-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="dfb55-116">MouseOver</span></span>|<span data-ttu-id="dfb55-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-117">CommonStates</span></span>|<span data-ttu-id="dfb55-118">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="dfb55-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="dfb55-119">Отключено</span><span class="sxs-lookup"><span data-stu-id="dfb55-119">Disabled</span></span>|<span data-ttu-id="dfb55-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-120">CommonStates</span></span>|<span data-ttu-id="dfb55-121">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="dfb55-121">The control is disabled.</span></span>|  
|<span data-ttu-id="dfb55-122">Focused</span><span class="sxs-lookup"><span data-stu-id="dfb55-122">Focused</span></span>|<span data-ttu-id="dfb55-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-123">FocusStates</span></span>|<span data-ttu-id="dfb55-124">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="dfb55-124">The control has focus.</span></span>|  
|<span data-ttu-id="dfb55-125">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="dfb55-125">Unfocused</span></span>|<span data-ttu-id="dfb55-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-126">FocusStates</span></span>|<span data-ttu-id="dfb55-127">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="dfb55-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="dfb55-128">Развернуто</span><span class="sxs-lookup"><span data-stu-id="dfb55-128">Expanded</span></span>|<span data-ttu-id="dfb55-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-129">ExpansionStates</span></span>|<span data-ttu-id="dfb55-130">Элемент управления развернут.</span><span class="sxs-lookup"><span data-stu-id="dfb55-130">The control is expanded.</span></span>|  
|<span data-ttu-id="dfb55-131">Свернуто</span><span class="sxs-lookup"><span data-stu-id="dfb55-131">Collapsed</span></span>|<span data-ttu-id="dfb55-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-132">ExpansionStates</span></span>|<span data-ttu-id="dfb55-133">Элемент управления не развернут.</span><span class="sxs-lookup"><span data-stu-id="dfb55-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="dfb55-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="dfb55-134">ExpandDown</span></span>|<span data-ttu-id="dfb55-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-135">ExpandDirectionStates</span></span>|<span data-ttu-id="dfb55-136">Элемент управления расширяется вниз.</span><span class="sxs-lookup"><span data-stu-id="dfb55-136">The control expands down.</span></span>|  
|<span data-ttu-id="dfb55-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="dfb55-137">ExpandUp</span></span>|<span data-ttu-id="dfb55-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-138">ExpandDirectionStates</span></span>|<span data-ttu-id="dfb55-139">Элемент управления расширяется вверх.</span><span class="sxs-lookup"><span data-stu-id="dfb55-139">The control expands up.</span></span>|  
|<span data-ttu-id="dfb55-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="dfb55-140">ExpandLeft</span></span>|<span data-ttu-id="dfb55-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-141">ExpandDirectionStates</span></span>|<span data-ttu-id="dfb55-142">Элемент управления расширяется влево.</span><span class="sxs-lookup"><span data-stu-id="dfb55-142">The control expands left.</span></span>|  
|<span data-ttu-id="dfb55-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="dfb55-143">ExpandRight</span></span>|<span data-ttu-id="dfb55-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-144">ExpandDirectionStates</span></span>|<span data-ttu-id="dfb55-145">Элемент управления расширяется вправо.</span><span class="sxs-lookup"><span data-stu-id="dfb55-145">The control expands right.</span></span>|  
|<span data-ttu-id="dfb55-146">Valid</span><span class="sxs-lookup"><span data-stu-id="dfb55-146">Valid</span></span>|<span data-ttu-id="dfb55-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-147">ValidationStates</span></span>|<span data-ttu-id="dfb55-148">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="dfb55-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="dfb55-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="dfb55-149">InvalidFocused</span></span>|<span data-ttu-id="dfb55-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-150">ValidationStates</span></span>|<span data-ttu-id="dfb55-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="dfb55-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="dfb55-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="dfb55-152">InvalidUnfocused</span></span>|<span data-ttu-id="dfb55-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dfb55-153">ValidationStates</span></span>|<span data-ttu-id="dfb55-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="dfb55-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="dfb55-155">Пример шаблона элемента управления Expander</span><span class="sxs-lookup"><span data-stu-id="dfb55-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="dfb55-156">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Expander> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dfb55-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="dfb55-157">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dfb55-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="dfb55-158">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="dfb55-158">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb55-159">См. также</span><span class="sxs-lookup"><span data-stu-id="dfb55-159">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="dfb55-160">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="dfb55-160">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="dfb55-161">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="dfb55-161">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="dfb55-162">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="dfb55-162">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="dfb55-163">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="dfb55-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
