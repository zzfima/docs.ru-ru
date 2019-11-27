---
title: Стили и шаблоны элемента ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283453"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="e27ac-102">Стили и шаблоны элемента ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e27ac-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="e27ac-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e27ac-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="e27ac-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e27ac-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e27ac-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="e27ac-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="e27ac-106">Части ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e27ac-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="e27ac-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e27ac-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="e27ac-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="e27ac-108">Part</span></span>|<span data-ttu-id="e27ac-109">Тип</span><span class="sxs-lookup"><span data-stu-id="e27ac-109">Type</span></span>|<span data-ttu-id="e27ac-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e27ac-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e27ac-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="e27ac-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e27ac-112">Объект, указывающий ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="e27ac-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="e27ac-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="e27ac-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e27ac-114">Объект, определяющий путь индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="e27ac-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="e27ac-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="e27ac-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="e27ac-116">Объект, надстрочные индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="e27ac-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="e27ac-117">Состояния ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e27ac-117">ProgressBar States</span></span>  
 <span data-ttu-id="e27ac-118">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e27ac-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="e27ac-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e27ac-119">VisualState Name</span></span>|<span data-ttu-id="e27ac-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e27ac-120">VisualStateGroup Name</span></span>|<span data-ttu-id="e27ac-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e27ac-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="e27ac-122">Завершение работы</span><span class="sxs-lookup"><span data-stu-id="e27ac-122">Determinate</span></span>|<span data-ttu-id="e27ac-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e27ac-123">CommonStates</span></span>|<span data-ttu-id="e27ac-124"><xref:System.Windows.Controls.ProgressBar> отчет о ходе выполнения на основе свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="e27ac-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="e27ac-125">Неопределенному</span><span class="sxs-lookup"><span data-stu-id="e27ac-125">Indeterminate</span></span>|<span data-ttu-id="e27ac-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e27ac-126">CommonStates</span></span>|<span data-ttu-id="e27ac-127"><xref:System.Windows.Controls.ProgressBar> сообщает об общем ходе выполнения с повторяющимся шаблоном.</span><span class="sxs-lookup"><span data-stu-id="e27ac-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="e27ac-128">Valid</span><span class="sxs-lookup"><span data-stu-id="e27ac-128">Valid</span></span>|<span data-ttu-id="e27ac-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e27ac-129">ValidationStates</span></span>|<span data-ttu-id="e27ac-130">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="e27ac-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e27ac-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e27ac-131">InvalidFocused</span></span>|<span data-ttu-id="e27ac-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e27ac-132">ValidationStates</span></span>|<span data-ttu-id="e27ac-133">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e27ac-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e27ac-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e27ac-134">InvalidUnfocused</span></span>|<span data-ttu-id="e27ac-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e27ac-135">ValidationStates</span></span>|<span data-ttu-id="e27ac-136">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e27ac-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="e27ac-137">Пример объекта ControlTemplate для элемента ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e27ac-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e27ac-138">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="e27ac-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="e27ac-139">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e27ac-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e27ac-140">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e27ac-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27ac-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e27ac-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e27ac-142">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e27ac-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e27ac-143">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e27ac-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e27ac-144">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e27ac-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e27ac-145">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="e27ac-145">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
