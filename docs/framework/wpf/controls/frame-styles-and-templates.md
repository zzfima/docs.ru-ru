---
title: "Стили и шаблоны элемента Frame"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 603c4f766b836c7a301cc151112457ddb0972d10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="ed771-102">Стили и шаблоны элемента Frame</span><span class="sxs-lookup"><span data-stu-id="ed771-102">Frame Styles and Templates</span></span>
<span data-ttu-id="ed771-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed771-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="ed771-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed771-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ed771-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ed771-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="ed771-106">Части фрейма</span><span class="sxs-lookup"><span data-stu-id="ed771-106">Frame Parts</span></span>  
 <span data-ttu-id="ed771-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed771-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="ed771-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="ed771-108">Part</span></span>|<span data-ttu-id="ed771-109">Тип</span><span class="sxs-lookup"><span data-stu-id="ed771-109">Type</span></span>|<span data-ttu-id="ed771-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ed771-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ed771-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="ed771-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="ed771-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="ed771-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="ed771-113">Состояния кадра</span><span class="sxs-lookup"><span data-stu-id="ed771-113">Frame States</span></span>  
 <span data-ttu-id="ed771-114">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed771-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="ed771-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="ed771-115">VisualState Name</span></span>|<span data-ttu-id="ed771-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ed771-116">VisualStateGroup Name</span></span>|<span data-ttu-id="ed771-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ed771-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ed771-118">Valid</span><span class="sxs-lookup"><span data-stu-id="ed771-118">Valid</span></span>|<span data-ttu-id="ed771-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed771-119">ValidationStates</span></span>|<span data-ttu-id="ed771-120">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="ed771-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ed771-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ed771-121">InvalidFocused</span></span>|<span data-ttu-id="ed771-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed771-122">ValidationStates</span></span>|<span data-ttu-id="ed771-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ed771-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ed771-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ed771-124">InvalidUnfocused</span></span>|<span data-ttu-id="ed771-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed771-125">ValidationStates</span></span>|<span data-ttu-id="ed771-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ed771-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="ed771-127">Пример создания шаблона элемента управления</span><span class="sxs-lookup"><span data-stu-id="ed771-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="ed771-128">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed771-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="ed771-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ed771-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ed771-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="ed771-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed771-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ed771-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ed771-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="ed771-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ed771-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="ed771-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ed771-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="ed771-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ed771-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ed771-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
