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
ms.openlocfilehash: 5cd92a4cda40fd850824ae601821dab08c7389e6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370115"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="87449-102">Стили и шаблоны элемента ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="87449-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="87449-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="87449-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="87449-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="87449-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="87449-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="87449-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="87449-106">Элементы управления ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="87449-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="87449-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="87449-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="87449-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="87449-108">Part</span></span>|<span data-ttu-id="87449-109">Тип</span><span class="sxs-lookup"><span data-stu-id="87449-109">Type</span></span>|<span data-ttu-id="87449-110">Описание</span><span class="sxs-lookup"><span data-stu-id="87449-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="87449-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="87449-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="87449-112">Заполнитель для содержимого в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="87449-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="87449-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="87449-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="87449-114"><xref:System.Windows.Controls.Primitives.ScrollBar> Используется для прокрутки содержимого по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="87449-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="87449-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="87449-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="87449-116"><xref:System.Windows.Controls.Primitives.ScrollBar> Используется для прокрутки содержимого по вертикали.</span><span class="sxs-lookup"><span data-stu-id="87449-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="87449-117">Состояния ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="87449-117">ScrollViewer States</span></span>  
 <span data-ttu-id="87449-118">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="87449-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="87449-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="87449-119">VisualState Name</span></span>|<span data-ttu-id="87449-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="87449-120">VisualStateGroup Name</span></span>|<span data-ttu-id="87449-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="87449-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="87449-122">Valid</span><span class="sxs-lookup"><span data-stu-id="87449-122">Valid</span></span>|<span data-ttu-id="87449-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87449-123">ValidationStates</span></span>|<span data-ttu-id="87449-124">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="87449-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="87449-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="87449-125">InvalidFocused</span></span>|<span data-ttu-id="87449-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87449-126">ValidationStates</span></span>|<span data-ttu-id="87449-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="87449-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="87449-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="87449-128">InvalidUnfocused</span></span>|<span data-ttu-id="87449-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="87449-129">ValidationStates</span></span>|<span data-ttu-id="87449-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="87449-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="87449-131">Пример шаблона элемента управления ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="87449-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="87449-132">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ScrollViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="87449-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="87449-133">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="87449-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="87449-134">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="87449-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87449-135">См. также</span><span class="sxs-lookup"><span data-stu-id="87449-135">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="87449-136">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="87449-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="87449-137">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="87449-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="87449-138">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="87449-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="87449-139">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="87449-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
