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
ms.openlocfilehash: b54dcacf55a750d7c1253db20147d18de47d027e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283393"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="e8bfd-102">Стили и шаблоны элемента ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="e8bfd-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="e8bfd-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="e8bfd-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e8bfd-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="e8bfd-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="e8bfd-106">ScrollViewer части</span><span class="sxs-lookup"><span data-stu-id="e8bfd-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="e8bfd-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="e8bfd-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="e8bfd-108">Part</span></span>|<span data-ttu-id="e8bfd-109">Введите</span><span class="sxs-lookup"><span data-stu-id="e8bfd-109">Type</span></span>|<span data-ttu-id="e8bfd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e8bfd-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8bfd-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="e8bfd-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="e8bfd-112">Заполнитель для содержимого в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="e8bfd-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="e8bfd-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="e8bfd-114"><xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="e8bfd-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="e8bfd-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="e8bfd-116"><xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по вертикали.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="e8bfd-117">Состояния ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="e8bfd-117">ScrollViewer States</span></span>  
 <span data-ttu-id="e8bfd-118">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="e8bfd-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e8bfd-119">VisualState Name</span></span>|<span data-ttu-id="e8bfd-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e8bfd-120">VisualStateGroup Name</span></span>|<span data-ttu-id="e8bfd-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e8bfd-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8bfd-122">Valid</span><span class="sxs-lookup"><span data-stu-id="e8bfd-122">Valid</span></span>|<span data-ttu-id="e8bfd-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8bfd-123">ValidationStates</span></span>|<span data-ttu-id="e8bfd-124">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e8bfd-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e8bfd-125">InvalidFocused</span></span>|<span data-ttu-id="e8bfd-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8bfd-126">ValidationStates</span></span>|<span data-ttu-id="e8bfd-127">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e8bfd-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e8bfd-128">InvalidUnfocused</span></span>|<span data-ttu-id="e8bfd-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8bfd-129">ValidationStates</span></span>|<span data-ttu-id="e8bfd-130">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="e8bfd-131">Пример ControlTemplate ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="e8bfd-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="e8bfd-132">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="e8bfd-133">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e8bfd-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e8bfd-134">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e8bfd-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bfd-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e8bfd-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e8bfd-136">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e8bfd-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e8bfd-137">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e8bfd-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e8bfd-138">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e8bfd-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e8bfd-139">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="e8bfd-139">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
