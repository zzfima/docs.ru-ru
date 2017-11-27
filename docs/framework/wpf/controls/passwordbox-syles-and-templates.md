---
title: "Стили и шаблоны элемента PasswordBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17a9292ef6aeba157780be5ec87d67725eb833a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="bab4a-102">Стили и шаблоны элемента PasswordBox</span><span class="sxs-lookup"><span data-stu-id="bab4a-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="bab4a-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="bab4a-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bab4a-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="bab4a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="bab4a-106">Поле пароля частей</span><span class="sxs-lookup"><span data-stu-id="bab4a-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="bab4a-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="bab4a-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="bab4a-108">Part</span></span>|<span data-ttu-id="bab4a-109">Тип</span><span class="sxs-lookup"><span data-stu-id="bab4a-109">Type</span></span>|<span data-ttu-id="bab4a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bab4a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bab4a-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="bab4a-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="bab4a-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="bab4a-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="bab4a-113">Текст <xref:System.Windows.Controls.PasswordBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="bab4a-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="bab4a-114">Поле пароля состояний</span><span class="sxs-lookup"><span data-stu-id="bab4a-114">PasswordBox States</span></span>  
 <span data-ttu-id="bab4a-115">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="bab4a-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="bab4a-116">VisualState Name</span></span>|<span data-ttu-id="bab4a-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="bab4a-117">VisualStateGroup Name</span></span>|<span data-ttu-id="bab4a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bab4a-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bab4a-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="bab4a-119">Normal</span></span>|<span data-ttu-id="bab4a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-120">CommonStates</span></span>|<span data-ttu-id="bab4a-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bab4a-121">The default state.</span></span>|  
|<span data-ttu-id="bab4a-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bab4a-122">MouseOver</span></span>|<span data-ttu-id="bab4a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-123">CommonStates</span></span>|<span data-ttu-id="bab4a-124">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="bab4a-125">Отключено</span><span class="sxs-lookup"><span data-stu-id="bab4a-125">Disabled</span></span>|<span data-ttu-id="bab4a-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-126">CommonStates</span></span>|<span data-ttu-id="bab4a-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="bab4a-127">The control is disabled.</span></span>|  
|<span data-ttu-id="bab4a-128">Focused</span><span class="sxs-lookup"><span data-stu-id="bab4a-128">Focused</span></span>|<span data-ttu-id="bab4a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-129">FocusStates</span></span>|<span data-ttu-id="bab4a-130">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="bab4a-130">The control has focus.</span></span>|  
|<span data-ttu-id="bab4a-131">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="bab4a-131">Unfocused</span></span>|<span data-ttu-id="bab4a-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-132">FocusStates</span></span>|<span data-ttu-id="bab4a-133">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="bab4a-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="bab4a-134">Valid</span><span class="sxs-lookup"><span data-stu-id="bab4a-134">Valid</span></span>|<span data-ttu-id="bab4a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-135">ValidationStates</span></span>|<span data-ttu-id="bab4a-136">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="bab4a-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bab4a-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bab4a-137">InvalidFocused</span></span>|<span data-ttu-id="bab4a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-138">ValidationStates</span></span>|<span data-ttu-id="bab4a-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="bab4a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bab4a-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bab4a-140">InvalidUnfocused</span></span>|<span data-ttu-id="bab4a-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bab4a-141">ValidationStates</span></span>|<span data-ttu-id="bab4a-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="bab4a-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="bab4a-143">Пример шаблона элемента управления PasswordBox</span><span class="sxs-lookup"><span data-stu-id="bab4a-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="bab4a-144">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bab4a-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="bab4a-145">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bab4a-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bab4a-146">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="bab4a-146">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab4a-147">См. также</span><span class="sxs-lookup"><span data-stu-id="bab4a-147">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="bab4a-148">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="bab4a-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="bab4a-149">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="bab4a-149">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="bab4a-150">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="bab4a-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="bab4a-151">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="bab4a-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
