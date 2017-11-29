---
title: "Стили и шаблоны элемента RepeatButton"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4895757e909d5e15fd6540b19e1eeec414e1f4e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="repeatbutton-syles-and-templates"></a><span data-ttu-id="5c1cd-102">Стили и шаблоны элемента RepeatButton</span><span class="sxs-lookup"><span data-stu-id="5c1cd-102">RepeatButton Syles and Templates</span></span>
<span data-ttu-id="5c1cd-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="5c1cd-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5c1cd-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="5c1cd-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="repeatbutton-parts"></a><span data-ttu-id="5c1cd-106">RepeatButton частей</span><span class="sxs-lookup"><span data-stu-id="5c1cd-106">RepeatButton Parts</span></span>  
 <span data-ttu-id="5c1cd-107"><xref:System.Windows.Controls.Primitives.RepeatButton> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>  
  
## <a name="repeatbutton-states"></a><span data-ttu-id="5c1cd-108">RepeatButton состояний</span><span class="sxs-lookup"><span data-stu-id="5c1cd-108">RepeatButton States</span></span>  
 <span data-ttu-id="5c1cd-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
|<span data-ttu-id="5c1cd-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="5c1cd-110">VisualState Name</span></span>|<span data-ttu-id="5c1cd-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5c1cd-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5c1cd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5c1cd-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5c1cd-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-113">Normal</span></span>|<span data-ttu-id="5c1cd-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-114">CommonStates</span></span>|<span data-ttu-id="5c1cd-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-115">The default state.</span></span>|  
|<span data-ttu-id="5c1cd-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5c1cd-116">MouseOver</span></span>|<span data-ttu-id="5c1cd-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-117">CommonStates</span></span>|<span data-ttu-id="5c1cd-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="5c1cd-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="5c1cd-119">Pressed</span></span>|<span data-ttu-id="5c1cd-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-120">CommonStates</span></span>|<span data-ttu-id="5c1cd-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-121">The control is pressed.</span></span>|  
|<span data-ttu-id="5c1cd-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="5c1cd-122">Disabled</span></span>|<span data-ttu-id="5c1cd-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-123">CommonStates</span></span>|<span data-ttu-id="5c1cd-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-124">The control is disabled.</span></span>|  
|<span data-ttu-id="5c1cd-125">Focused</span><span class="sxs-lookup"><span data-stu-id="5c1cd-125">Focused</span></span>|<span data-ttu-id="5c1cd-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-126">FocusStates</span></span>|<span data-ttu-id="5c1cd-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-127">The control has focus.</span></span>|  
|<span data-ttu-id="5c1cd-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="5c1cd-128">Unfocused</span></span>|<span data-ttu-id="5c1cd-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-129">FocusStates</span></span>|<span data-ttu-id="5c1cd-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="5c1cd-131">Valid</span><span class="sxs-lookup"><span data-stu-id="5c1cd-131">Valid</span></span>|<span data-ttu-id="5c1cd-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-132">ValidationStates</span></span>|<span data-ttu-id="5c1cd-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5c1cd-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5c1cd-134">InvalidFocused</span></span>|<span data-ttu-id="5c1cd-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-135">ValidationStates</span></span>|<span data-ttu-id="5c1cd-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5c1cd-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5c1cd-137">InvalidUnfocused</span></span>|<span data-ttu-id="5c1cd-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5c1cd-138">ValidationStates</span></span>|<span data-ttu-id="5c1cd-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="5c1cd-140">Пример шаблона элемента управления RepeatButton</span><span class="sxs-lookup"><span data-stu-id="5c1cd-140">RepeatButton ControlTemplate Example</span></span>  
 <span data-ttu-id="5c1cd-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.RepeatButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RepeatButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]  
  
 <span data-ttu-id="5c1cd-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5c1cd-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5c1cd-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="5c1cd-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1cd-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5c1cd-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="5c1cd-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="5c1cd-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="5c1cd-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="5c1cd-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="5c1cd-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="5c1cd-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="5c1cd-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5c1cd-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
