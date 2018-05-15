---
title: Стили и шаблоны элемента Label
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: a56b03d2b851f518dc76dd07e5d182688da7111d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="84967-102">Стили и шаблоны элемента Label</span><span class="sxs-lookup"><span data-stu-id="84967-102">Label Styles and Templates</span></span>
<span data-ttu-id="84967-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84967-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="84967-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84967-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="84967-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="84967-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="84967-106">Метка части</span><span class="sxs-lookup"><span data-stu-id="84967-106">Label Parts</span></span>  
 <span data-ttu-id="84967-107"><xref:System.Windows.Controls.Label> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="84967-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="84967-108">Метка состояния</span><span class="sxs-lookup"><span data-stu-id="84967-108">Label States</span></span>  
 <span data-ttu-id="84967-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84967-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="84967-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="84967-110">VisualState Name</span></span>|<span data-ttu-id="84967-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="84967-111">VisualStateGroup Name</span></span>|<span data-ttu-id="84967-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84967-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="84967-113">Valid</span><span class="sxs-lookup"><span data-stu-id="84967-113">Valid</span></span>|<span data-ttu-id="84967-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84967-114">ValidationStates</span></span>|<span data-ttu-id="84967-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="84967-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="84967-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="84967-116">InvalidFocused</span></span>|<span data-ttu-id="84967-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84967-117">ValidationStates</span></span>|<span data-ttu-id="84967-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="84967-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="84967-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="84967-119">InvalidUnfocused</span></span>|<span data-ttu-id="84967-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="84967-120">ValidationStates</span></span>|<span data-ttu-id="84967-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="84967-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="84967-122">Пример шаблона элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="84967-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="84967-123">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="84967-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="84967-124"><xref:System.Windows.Controls.ControlTemplate> Используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="84967-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="84967-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="84967-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84967-126">См. также</span><span class="sxs-lookup"><span data-stu-id="84967-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="84967-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="84967-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="84967-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="84967-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="84967-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="84967-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="84967-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="84967-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
