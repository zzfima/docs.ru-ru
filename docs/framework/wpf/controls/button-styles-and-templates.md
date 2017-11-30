---
title: "Стили и шаблоны элемента Button"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27d68cd4102e8ba8502f1be5a9709082fa3d9ff3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="898c4-102">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="898c4-102">Button Styles and Templates</span></span>
<span data-ttu-id="898c4-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="898c4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="898c4-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="898c4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="898c4-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="898c4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="898c4-106">Кнопка частей</span><span class="sxs-lookup"><span data-stu-id="898c4-106">Button Parts</span></span>  
 <span data-ttu-id="898c4-107"><xref:System.Windows.Controls.Button> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="898c4-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="898c4-108">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="898c4-108">Button States</span></span>  
 <span data-ttu-id="898c4-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="898c4-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="898c4-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="898c4-110">VisualState Name</span></span>|<span data-ttu-id="898c4-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="898c4-111">VisualStateGroup Name</span></span>|<span data-ttu-id="898c4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="898c4-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="898c4-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="898c4-113">Normal</span></span>|<span data-ttu-id="898c4-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="898c4-114">CommonStates</span></span>|<span data-ttu-id="898c4-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="898c4-115">The default state.</span></span>|  
|<span data-ttu-id="898c4-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="898c4-116">MouseOver</span></span>|<span data-ttu-id="898c4-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="898c4-117">CommonStates</span></span>|<span data-ttu-id="898c4-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="898c4-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="898c4-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="898c4-119">Pressed</span></span>|<span data-ttu-id="898c4-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="898c4-120">CommonStates</span></span>|<span data-ttu-id="898c4-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="898c4-121">The control is pressed.</span></span>|  
|<span data-ttu-id="898c4-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="898c4-122">Disabled</span></span>|<span data-ttu-id="898c4-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="898c4-123">CommonStates</span></span>|<span data-ttu-id="898c4-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="898c4-124">The control is disabled.</span></span>|  
|<span data-ttu-id="898c4-125">Focused</span><span class="sxs-lookup"><span data-stu-id="898c4-125">Focused</span></span>|<span data-ttu-id="898c4-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="898c4-126">FocusStates</span></span>|<span data-ttu-id="898c4-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="898c4-127">The control has focus.</span></span>|  
|<span data-ttu-id="898c4-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="898c4-128">Unfocused</span></span>|<span data-ttu-id="898c4-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="898c4-129">FocusStates</span></span>|<span data-ttu-id="898c4-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="898c4-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="898c4-131">Valid</span><span class="sxs-lookup"><span data-stu-id="898c4-131">Valid</span></span>|<span data-ttu-id="898c4-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="898c4-132">ValidationStates</span></span>|<span data-ttu-id="898c4-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="898c4-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="898c4-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="898c4-134">InvalidFocused</span></span>|<span data-ttu-id="898c4-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="898c4-135">ValidationStates</span></span>|<span data-ttu-id="898c4-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="898c4-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="898c4-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="898c4-137">InvalidUnfocused</span></span>|<span data-ttu-id="898c4-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="898c4-138">ValidationStates</span></span>|<span data-ttu-id="898c4-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="898c4-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="898c4-140">Пример шаблона элемента управления кнопки</span><span class="sxs-lookup"><span data-stu-id="898c4-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="898c4-141">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="898c4-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="898c4-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="898c4-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="898c4-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="898c4-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898c4-144">См. также</span><span class="sxs-lookup"><span data-stu-id="898c4-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="898c4-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="898c4-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="898c4-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="898c4-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="898c4-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="898c4-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="898c4-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="898c4-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
