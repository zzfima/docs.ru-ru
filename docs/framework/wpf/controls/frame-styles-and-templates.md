---
title: Стили и шаблоны элемента Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 89f4fc21637d20ca226507463093bc6bae2241fc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460322"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="4a769-102">Стили и шаблоны элемента Frame</span><span class="sxs-lookup"><span data-stu-id="4a769-102">Frame Styles and Templates</span></span>
<span data-ttu-id="4a769-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="4a769-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="4a769-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4a769-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4a769-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4a769-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="4a769-106">Элементы рамки</span><span class="sxs-lookup"><span data-stu-id="4a769-106">Frame Parts</span></span>  
 <span data-ttu-id="4a769-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="4a769-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="4a769-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="4a769-108">Part</span></span>|<span data-ttu-id="4a769-109">Type</span><span class="sxs-lookup"><span data-stu-id="4a769-109">Type</span></span>|<span data-ttu-id="4a769-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4a769-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4a769-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="4a769-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="4a769-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="4a769-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="4a769-113">Состояния кадров</span><span class="sxs-lookup"><span data-stu-id="4a769-113">Frame States</span></span>  
 <span data-ttu-id="4a769-114">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="4a769-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="4a769-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="4a769-115">VisualState Name</span></span>|<span data-ttu-id="4a769-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4a769-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4a769-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4a769-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4a769-118">Valid</span><span class="sxs-lookup"><span data-stu-id="4a769-118">Valid</span></span>|<span data-ttu-id="4a769-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a769-119">ValidationStates</span></span>|<span data-ttu-id="4a769-120">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="4a769-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4a769-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4a769-121">InvalidFocused</span></span>|<span data-ttu-id="4a769-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a769-122">ValidationStates</span></span>|<span data-ttu-id="4a769-123">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="4a769-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4a769-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4a769-124">InvalidUnfocused</span></span>|<span data-ttu-id="4a769-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a769-125">ValidationStates</span></span>|<span data-ttu-id="4a769-126">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="4a769-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="4a769-127">Пример ControlTemplate в кадре</span><span class="sxs-lookup"><span data-stu-id="4a769-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="4a769-128">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="4a769-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="4a769-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4a769-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4a769-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4a769-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a769-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4a769-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4a769-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="4a769-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4a769-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="4a769-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4a769-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="4a769-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4a769-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4a769-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
