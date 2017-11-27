---
title: "Стили и шаблоны элемента TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f5cfd1c0715c7f9610f85201cd40a3973a2be64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="74479-102">Стили и шаблоны элемента TextBox</span><span class="sxs-lookup"><span data-stu-id="74479-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="74479-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="74479-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="74479-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="74479-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="74479-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="74479-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="74479-106">Части текстового поля</span><span class="sxs-lookup"><span data-stu-id="74479-106">TextBox Parts</span></span>  
 <span data-ttu-id="74479-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="74479-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="74479-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="74479-108">Part</span></span>|<span data-ttu-id="74479-109">Тип</span><span class="sxs-lookup"><span data-stu-id="74479-109">Type</span></span>|<span data-ttu-id="74479-110">Описание</span><span class="sxs-lookup"><span data-stu-id="74479-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="74479-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="74479-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="74479-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="74479-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="74479-113">Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="74479-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="74479-114">Текстовое поле состояния</span><span class="sxs-lookup"><span data-stu-id="74479-114">TextBox States</span></span>  
 <span data-ttu-id="74479-115">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="74479-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="74479-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="74479-116">VisualState Name</span></span>|<span data-ttu-id="74479-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="74479-117">VisualStateGroup Name</span></span>|<span data-ttu-id="74479-118">Описание</span><span class="sxs-lookup"><span data-stu-id="74479-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="74479-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="74479-119">Normal</span></span>|<span data-ttu-id="74479-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="74479-120">CommonStates</span></span>|<span data-ttu-id="74479-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="74479-121">The default state.</span></span>|  
|<span data-ttu-id="74479-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="74479-122">MouseOver</span></span>|<span data-ttu-id="74479-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="74479-123">CommonStates</span></span>|<span data-ttu-id="74479-124">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="74479-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="74479-125">Отключено</span><span class="sxs-lookup"><span data-stu-id="74479-125">Disabled</span></span>|<span data-ttu-id="74479-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="74479-126">CommonStates</span></span>|<span data-ttu-id="74479-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="74479-127">The control is disabled.</span></span>|  
|<span data-ttu-id="74479-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="74479-128">ReadOnly</span></span>|<span data-ttu-id="74479-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="74479-129">CommonStates</span></span>|<span data-ttu-id="74479-130">Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="74479-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="74479-131">Focused</span><span class="sxs-lookup"><span data-stu-id="74479-131">Focused</span></span>|<span data-ttu-id="74479-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="74479-132">FocusStates</span></span>|<span data-ttu-id="74479-133">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="74479-133">The control has focus.</span></span>|  
|<span data-ttu-id="74479-134">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="74479-134">Unfocused</span></span>|<span data-ttu-id="74479-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="74479-135">FocusStates</span></span>|<span data-ttu-id="74479-136">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="74479-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="74479-137">Valid</span><span class="sxs-lookup"><span data-stu-id="74479-137">Valid</span></span>|<span data-ttu-id="74479-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="74479-138">ValidationStates</span></span>|<span data-ttu-id="74479-139">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="74479-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="74479-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="74479-140">InvalidFocused</span></span>|<span data-ttu-id="74479-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="74479-141">ValidationStates</span></span>|<span data-ttu-id="74479-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="74479-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="74479-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="74479-143">InvalidUnfocused</span></span>|<span data-ttu-id="74479-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="74479-144">ValidationStates</span></span>|<span data-ttu-id="74479-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="74479-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="74479-146">Пример шаблона элемента управления TextBox</span><span class="sxs-lookup"><span data-stu-id="74479-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="74479-147">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="74479-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="74479-148">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="74479-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="74479-149">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="74479-149">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74479-150">См. также</span><span class="sxs-lookup"><span data-stu-id="74479-150">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="74479-151">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="74479-151">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="74479-152">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="74479-152">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="74479-153">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="74479-153">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="74479-154">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="74479-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
