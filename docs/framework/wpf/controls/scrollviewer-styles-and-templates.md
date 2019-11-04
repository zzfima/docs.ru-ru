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
ms.openlocfilehash: 70a2002ab114f2bbd6a4e550ae9006e214ee27a5
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458416"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="9f181-102">Стили и шаблоны элемента ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="9f181-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="9f181-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9f181-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="9f181-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9f181-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9f181-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="9f181-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="9f181-106">ScrollViewer части</span><span class="sxs-lookup"><span data-stu-id="9f181-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="9f181-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9f181-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="9f181-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="9f181-108">Part</span></span>|<span data-ttu-id="9f181-109">Type</span><span class="sxs-lookup"><span data-stu-id="9f181-109">Type</span></span>|<span data-ttu-id="9f181-110">Описание</span><span class="sxs-lookup"><span data-stu-id="9f181-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f181-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="9f181-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="9f181-112">Заполнитель для содержимого в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9f181-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="9f181-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="9f181-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="9f181-114"><xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="9f181-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="9f181-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="9f181-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="9f181-116"><xref:System.Windows.Controls.Primitives.ScrollBar>, используемый для прокрутки содержимого по вертикали.</span><span class="sxs-lookup"><span data-stu-id="9f181-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="9f181-117">Состояния ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="9f181-117">ScrollViewer States</span></span>  
 <span data-ttu-id="9f181-118">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9f181-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="9f181-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="9f181-119">VisualState Name</span></span>|<span data-ttu-id="9f181-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="9f181-120">VisualStateGroup Name</span></span>|<span data-ttu-id="9f181-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9f181-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f181-122">Valid</span><span class="sxs-lookup"><span data-stu-id="9f181-122">Valid</span></span>|<span data-ttu-id="9f181-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f181-123">ValidationStates</span></span>|<span data-ttu-id="9f181-124">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="9f181-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9f181-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9f181-125">InvalidFocused</span></span>|<span data-ttu-id="9f181-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f181-126">ValidationStates</span></span>|<span data-ttu-id="9f181-127">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="9f181-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9f181-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9f181-128">InvalidUnfocused</span></span>|<span data-ttu-id="9f181-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f181-129">ValidationStates</span></span>|<span data-ttu-id="9f181-130">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="9f181-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="9f181-131">Пример ControlTemplate ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="9f181-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="9f181-132">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="9f181-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="9f181-133">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9f181-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9f181-134">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="9f181-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f181-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9f181-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9f181-136">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="9f181-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9f181-137">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="9f181-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9f181-138">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="9f181-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9f181-139">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9f181-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
