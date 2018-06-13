---
title: Стили и шаблоны элемента ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 5ad3738972ae9b33764d3b710077f6d4a0526a13
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457734"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="59293-102">Стили и шаблоны элемента ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="59293-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="59293-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59293-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="59293-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59293-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="59293-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="59293-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="59293-106">Элементы управления ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="59293-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="59293-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59293-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="59293-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="59293-108">Part</span></span>|<span data-ttu-id="59293-109">Тип</span><span class="sxs-lookup"><span data-stu-id="59293-109">Type</span></span>|<span data-ttu-id="59293-110">Описание</span><span class="sxs-lookup"><span data-stu-id="59293-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="59293-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="59293-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="59293-112">Заполнитель для содержимого в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="59293-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="59293-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="59293-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="59293-114"><xref:System.Windows.Controls.Primitives.ScrollBar> Используется для прокрутки содержимого по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="59293-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="59293-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="59293-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="59293-116"><xref:System.Windows.Controls.Primitives.ScrollBar> Используется для прокрутки содержимого по вертикали.</span><span class="sxs-lookup"><span data-stu-id="59293-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="59293-117">ScrollViewer состояний</span><span class="sxs-lookup"><span data-stu-id="59293-117">ScrollViewer States</span></span>  
 <span data-ttu-id="59293-118">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59293-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="59293-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="59293-119">VisualState Name</span></span>|<span data-ttu-id="59293-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="59293-120">VisualStateGroup Name</span></span>|<span data-ttu-id="59293-121">Описание</span><span class="sxs-lookup"><span data-stu-id="59293-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="59293-122">Valid</span><span class="sxs-lookup"><span data-stu-id="59293-122">Valid</span></span>|<span data-ttu-id="59293-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="59293-123">ValidationStates</span></span>|<span data-ttu-id="59293-124">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="59293-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="59293-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="59293-125">InvalidFocused</span></span>|<span data-ttu-id="59293-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="59293-126">ValidationStates</span></span>|<span data-ttu-id="59293-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="59293-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="59293-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="59293-128">InvalidUnfocused</span></span>|<span data-ttu-id="59293-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="59293-129">ValidationStates</span></span>|<span data-ttu-id="59293-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="59293-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="59293-131">Пример шаблона элемента управления ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="59293-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="59293-132">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59293-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="59293-133">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="59293-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="59293-134">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="59293-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59293-135">См. также</span><span class="sxs-lookup"><span data-stu-id="59293-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="59293-136">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="59293-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="59293-137">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="59293-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="59293-138">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="59293-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="59293-139">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="59293-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
