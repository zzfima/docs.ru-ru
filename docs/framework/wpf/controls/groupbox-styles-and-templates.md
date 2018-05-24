---
title: Стили и шаблоны элемента GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 539bf5b0ef8772ea469123442d152726d0948be9
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="1d1a5-102">Стили и шаблоны элемента GroupBox</span><span class="sxs-lookup"><span data-stu-id="1d1a5-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="1d1a5-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="1d1a5-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1d1a5-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="1d1a5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="1d1a5-106">GroupBox частей</span><span class="sxs-lookup"><span data-stu-id="1d1a5-106">GroupBox Parts</span></span>  
 <span data-ttu-id="1d1a5-107"><xref:System.Windows.Controls.GroupBox> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="1d1a5-108">GroupBox состояний</span><span class="sxs-lookup"><span data-stu-id="1d1a5-108">GroupBox States</span></span>  
 <span data-ttu-id="1d1a5-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="1d1a5-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="1d1a5-110">VisualState Name</span></span>|<span data-ttu-id="1d1a5-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1d1a5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="1d1a5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1d1a5-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1d1a5-113">Valid</span><span class="sxs-lookup"><span data-stu-id="1d1a5-113">Valid</span></span>|<span data-ttu-id="1d1a5-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1d1a5-114">ValidationStates</span></span>|<span data-ttu-id="1d1a5-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1d1a5-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1d1a5-116">InvalidFocused</span></span>|<span data-ttu-id="1d1a5-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1d1a5-117">ValidationStates</span></span>|<span data-ttu-id="1d1a5-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1d1a5-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1d1a5-119">InvalidUnfocused</span></span>|<span data-ttu-id="1d1a5-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1d1a5-120">ValidationStates</span></span>|<span data-ttu-id="1d1a5-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="1d1a5-122">Пример шаблона элемента управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="1d1a5-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="1d1a5-123">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="1d1a5-124"><xref:System.Windows.Controls.ControlTemplate> Используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d1a5-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1d1a5-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1d1a5-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d1a5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1d1a5-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="1d1a5-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="1d1a5-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="1d1a5-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="1d1a5-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="1d1a5-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="1d1a5-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="1d1a5-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="1d1a5-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
