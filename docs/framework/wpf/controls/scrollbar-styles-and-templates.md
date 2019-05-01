---
title: Стили и шаблоны элемента ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 22b2206067302f621a94a1e9abca1607792b3393
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052889"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="65d23-102">Стили и шаблоны элемента ScrollBar</span><span class="sxs-lookup"><span data-stu-id="65d23-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="65d23-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.ScrollBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="65d23-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="65d23-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="65d23-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="65d23-106">Части полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="65d23-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="65d23-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Primitives.ScrollBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="65d23-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="65d23-108">Part</span></span>|<span data-ttu-id="65d23-109">Тип</span><span class="sxs-lookup"><span data-stu-id="65d23-109">Type</span></span>|<span data-ttu-id="65d23-110">Описание</span><span class="sxs-lookup"><span data-stu-id="65d23-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="65d23-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="65d23-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="65d23-112">Контейнер для элемента, который указывает положение <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="65d23-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="65d23-113">Состояния полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="65d23-113">ScrollBar States</span></span>  
 <span data-ttu-id="65d23-114">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.ScrollBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="65d23-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="65d23-115">VisualState Name</span></span>|<span data-ttu-id="65d23-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="65d23-116">VisualStateGroup Name</span></span>|<span data-ttu-id="65d23-117">Описание</span><span class="sxs-lookup"><span data-stu-id="65d23-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="65d23-118">Норм.</span><span class="sxs-lookup"><span data-stu-id="65d23-118">Normal</span></span>|<span data-ttu-id="65d23-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d23-119">CommonStates</span></span>|<span data-ttu-id="65d23-120">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65d23-120">The default state.</span></span>|  
|<span data-ttu-id="65d23-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="65d23-121">MouseOver</span></span>|<span data-ttu-id="65d23-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d23-122">CommonStates</span></span>|<span data-ttu-id="65d23-123">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="65d23-124">Отключено</span><span class="sxs-lookup"><span data-stu-id="65d23-124">Disabled</span></span>|<span data-ttu-id="65d23-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d23-125">CommonStates</span></span>|<span data-ttu-id="65d23-126">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="65d23-126">The control is disabled.</span></span>|  
|<span data-ttu-id="65d23-127">Valid</span><span class="sxs-lookup"><span data-stu-id="65d23-127">Valid</span></span>|<span data-ttu-id="65d23-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d23-128">ValidationStates</span></span>|<span data-ttu-id="65d23-129">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="65d23-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="65d23-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="65d23-130">InvalidFocused</span></span>|<span data-ttu-id="65d23-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d23-131">ValidationStates</span></span>|<span data-ttu-id="65d23-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="65d23-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="65d23-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="65d23-133">InvalidUnfocused</span></span>|<span data-ttu-id="65d23-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d23-134">ValidationStates</span></span>|<span data-ttu-id="65d23-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="65d23-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="65d23-136">Пример шаблона элемента управления ScrollBar</span><span class="sxs-lookup"><span data-stu-id="65d23-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="65d23-137">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.ScrollBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="65d23-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="65d23-138">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="65d23-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="65d23-139">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="65d23-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d23-140">См. также</span><span class="sxs-lookup"><span data-stu-id="65d23-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="65d23-141">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="65d23-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="65d23-142">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="65d23-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="65d23-143">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="65d23-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="65d23-144">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="65d23-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
