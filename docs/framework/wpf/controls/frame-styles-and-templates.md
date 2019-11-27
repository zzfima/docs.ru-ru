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
ms.openlocfilehash: de853198c97c99319bea4a816c9a6eca5dc5d917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283732"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="1ddff-102">Стили и шаблоны элемента Frame</span><span class="sxs-lookup"><span data-stu-id="1ddff-102">Frame Styles and Templates</span></span>
<span data-ttu-id="1ddff-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="1ddff-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="1ddff-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ddff-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1ddff-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="1ddff-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="1ddff-106">Элементы рамки</span><span class="sxs-lookup"><span data-stu-id="1ddff-106">Frame Parts</span></span>  
 <span data-ttu-id="1ddff-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="1ddff-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1ddff-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="1ddff-108">Part</span></span>|<span data-ttu-id="1ddff-109">Тип</span><span class="sxs-lookup"><span data-stu-id="1ddff-109">Type</span></span>|<span data-ttu-id="1ddff-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1ddff-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1ddff-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="1ddff-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="1ddff-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="1ddff-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="1ddff-113">Состояния кадров</span><span class="sxs-lookup"><span data-stu-id="1ddff-113">Frame States</span></span>  
 <span data-ttu-id="1ddff-114">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="1ddff-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="1ddff-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="1ddff-115">VisualState Name</span></span>|<span data-ttu-id="1ddff-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1ddff-116">VisualStateGroup Name</span></span>|<span data-ttu-id="1ddff-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1ddff-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1ddff-118">Valid</span><span class="sxs-lookup"><span data-stu-id="1ddff-118">Valid</span></span>|<span data-ttu-id="1ddff-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1ddff-119">ValidationStates</span></span>|<span data-ttu-id="1ddff-120">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="1ddff-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1ddff-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1ddff-121">InvalidFocused</span></span>|<span data-ttu-id="1ddff-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1ddff-122">ValidationStates</span></span>|<span data-ttu-id="1ddff-123">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1ddff-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1ddff-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1ddff-124">InvalidUnfocused</span></span>|<span data-ttu-id="1ddff-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1ddff-125">ValidationStates</span></span>|<span data-ttu-id="1ddff-126">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="1ddff-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="1ddff-127">Пример ControlTemplate в кадре</span><span class="sxs-lookup"><span data-stu-id="1ddff-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="1ddff-128">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="1ddff-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="1ddff-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1ddff-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1ddff-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1ddff-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ddff-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1ddff-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1ddff-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="1ddff-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1ddff-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="1ddff-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1ddff-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="1ddff-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1ddff-135">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="1ddff-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
