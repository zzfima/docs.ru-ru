---
title: "Стили и шаблоны элемента ProgressBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6809ce2f51af8a1baf535afa8fe80f4e5b5f53e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="686e7-102">Стили и шаблоны элемента ProgressBar</span><span class="sxs-lookup"><span data-stu-id="686e7-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="686e7-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="686e7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="686e7-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="686e7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="686e7-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="686e7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="686e7-106">Части элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="686e7-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="686e7-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="686e7-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="686e7-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="686e7-108">Part</span></span>|<span data-ttu-id="686e7-109">Тип</span><span class="sxs-lookup"><span data-stu-id="686e7-109">Type</span></span>|<span data-ttu-id="686e7-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="686e7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="686e7-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="686e7-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="686e7-112">Объект, указывающий ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="686e7-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="686e7-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="686e7-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="686e7-114">Объект, определяющий путь индикатор хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="686e7-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="686e7-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="686e7-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="686e7-116">Объект, оформляющий индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="686e7-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="686e7-117">Состояния элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="686e7-117">ProgressBar States</span></span>  
 <span data-ttu-id="686e7-118">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="686e7-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="686e7-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="686e7-119">VisualState Name</span></span>|<span data-ttu-id="686e7-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="686e7-120">VisualStateGroup Name</span></span>|<span data-ttu-id="686e7-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="686e7-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="686e7-122">Определенный</span><span class="sxs-lookup"><span data-stu-id="686e7-122">Determinate</span></span>|<span data-ttu-id="686e7-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="686e7-123">CommonStates</span></span>|<span data-ttu-id="686e7-124"><xref:System.Windows.Controls.ProgressBar>сообщает о ходе выполнения на основе <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="686e7-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="686e7-125">Неопределенный</span><span class="sxs-lookup"><span data-stu-id="686e7-125">Indeterminate</span></span>|<span data-ttu-id="686e7-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="686e7-126">CommonStates</span></span>|<span data-ttu-id="686e7-127"><xref:System.Windows.Controls.ProgressBar>показывает общий ход выполнения с помощью повторяющегося рисунка.</span><span class="sxs-lookup"><span data-stu-id="686e7-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="686e7-128">Valid</span><span class="sxs-lookup"><span data-stu-id="686e7-128">Valid</span></span>|<span data-ttu-id="686e7-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="686e7-129">ValidationStates</span></span>|<span data-ttu-id="686e7-130">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="686e7-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="686e7-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="686e7-131">InvalidFocused</span></span>|<span data-ttu-id="686e7-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="686e7-132">ValidationStates</span></span>|<span data-ttu-id="686e7-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="686e7-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="686e7-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="686e7-134">InvalidUnfocused</span></span>|<span data-ttu-id="686e7-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="686e7-135">ValidationStates</span></span>|<span data-ttu-id="686e7-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="686e7-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="686e7-137">Пример шаблона элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="686e7-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="686e7-138">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="686e7-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="686e7-139">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="686e7-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="686e7-140">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="686e7-140">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="686e7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="686e7-141">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="686e7-142">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="686e7-142">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="686e7-143">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="686e7-143">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="686e7-144">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="686e7-144">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="686e7-145">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="686e7-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
