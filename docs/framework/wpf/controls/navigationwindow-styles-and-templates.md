---
title: "Стили и шаблоны элемента NavigationWindow"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b48b0b4451f0cf93b86ee448db255f337a859b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="7cc24-102">Стили и шаблоны элемента NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="7cc24-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="7cc24-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Navigation.NavigationWindow> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7cc24-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="7cc24-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7cc24-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7cc24-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="7cc24-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="7cc24-106">NavigationWindow частей</span><span class="sxs-lookup"><span data-stu-id="7cc24-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="7cc24-107">В следующей таблице перечислены именованные части <xref:System.Windows.Navigation.NavigationWindow> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7cc24-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="7cc24-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="7cc24-108">Part</span></span>|<span data-ttu-id="7cc24-109">Тип</span><span class="sxs-lookup"><span data-stu-id="7cc24-109">Type</span></span>|<span data-ttu-id="7cc24-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7cc24-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7cc24-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="7cc24-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="7cc24-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="7cc24-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="7cc24-113">NavigationWindow состояний</span><span class="sxs-lookup"><span data-stu-id="7cc24-113">NavigationWindow States</span></span>  
 <span data-ttu-id="7cc24-114">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Navigation.NavigationWindow> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7cc24-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="7cc24-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="7cc24-115">VisualState Name</span></span>|<span data-ttu-id="7cc24-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="7cc24-116">VisualStateGroup Name</span></span>|<span data-ttu-id="7cc24-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7cc24-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7cc24-118">Valid</span><span class="sxs-lookup"><span data-stu-id="7cc24-118">Valid</span></span>|<span data-ttu-id="7cc24-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7cc24-119">ValidationStates</span></span>|<span data-ttu-id="7cc24-120">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="7cc24-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7cc24-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7cc24-121">InvalidFocused</span></span>|<span data-ttu-id="7cc24-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7cc24-122">ValidationStates</span></span>|<span data-ttu-id="7cc24-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="7cc24-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7cc24-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7cc24-124">InvalidUnfocused</span></span>|<span data-ttu-id="7cc24-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7cc24-125">ValidationStates</span></span>|<span data-ttu-id="7cc24-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="7cc24-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="7cc24-127">Пример шаблона элемента управления NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="7cc24-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="7cc24-128">Несмотря на то, что этот пример содержит все элементы, определенные в <xref:System.Windows.Controls.ControlTemplate> из <xref:System.Windows.Navigation.NavigationWindow> по умолчанию, конкретные значения следует рассматривать в качестве примеров.</span><span class="sxs-lookup"><span data-stu-id="7cc24-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="7cc24-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7cc24-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7cc24-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="7cc24-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc24-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7cc24-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="7cc24-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="7cc24-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="7cc24-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="7cc24-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="7cc24-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="7cc24-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7cc24-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7cc24-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
