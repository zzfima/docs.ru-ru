---
title: "Стили и шаблоны элемента Window"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e1e623d9150f4848127cf662f583873e8e85f022
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="71a38-102">Стили и шаблоны элемента Window</span><span class="sxs-lookup"><span data-stu-id="71a38-102">Window Styles and Templates</span></span>
<span data-ttu-id="71a38-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="71a38-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="71a38-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="71a38-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="71a38-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="71a38-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="71a38-106">Элементы окна</span><span class="sxs-lookup"><span data-stu-id="71a38-106">Window Parts</span></span>  
 <span data-ttu-id="71a38-107"><xref:System.Windows.Window> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="71a38-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="71a38-108">Состояния окна</span><span class="sxs-lookup"><span data-stu-id="71a38-108">Window States</span></span>  
 <span data-ttu-id="71a38-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="71a38-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="71a38-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="71a38-110">VisualState Name</span></span>|<span data-ttu-id="71a38-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="71a38-111">VisualStateGroup Name</span></span>|<span data-ttu-id="71a38-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="71a38-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="71a38-113">Valid</span><span class="sxs-lookup"><span data-stu-id="71a38-113">Valid</span></span>|<span data-ttu-id="71a38-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="71a38-114">ValidationStates</span></span>|<span data-ttu-id="71a38-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="71a38-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="71a38-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="71a38-116">InvalidFocused</span></span>|<span data-ttu-id="71a38-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="71a38-117">ValidationStates</span></span>|<span data-ttu-id="71a38-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="71a38-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="71a38-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="71a38-119">InvalidUnfocused</span></span>|<span data-ttu-id="71a38-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="71a38-120">ValidationStates</span></span>|<span data-ttu-id="71a38-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="71a38-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="71a38-122">Пример шаблона элемента управления окна</span><span class="sxs-lookup"><span data-stu-id="71a38-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="71a38-123">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Window> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="71a38-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="71a38-124"><xref:System.Windows.Controls.ControlTemplate> Используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="71a38-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="71a38-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="71a38-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a38-126">См. также</span><span class="sxs-lookup"><span data-stu-id="71a38-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="71a38-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="71a38-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="71a38-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="71a38-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="71a38-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="71a38-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="71a38-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="71a38-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
