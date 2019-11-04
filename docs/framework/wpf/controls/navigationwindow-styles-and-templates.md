---
title: Стили и шаблоны элемента NavigationWindow
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 4aae14299b3959e7d2122991954cc62505d2a19e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460200"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="5bacb-102">Стили и шаблоны элемента NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="5bacb-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="5bacb-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="5bacb-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="5bacb-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bacb-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5bacb-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="5bacb-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="5bacb-106">NavigationWindow части</span><span class="sxs-lookup"><span data-stu-id="5bacb-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="5bacb-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="5bacb-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="5bacb-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="5bacb-108">Part</span></span>|<span data-ttu-id="5bacb-109">Type</span><span class="sxs-lookup"><span data-stu-id="5bacb-109">Type</span></span>|<span data-ttu-id="5bacb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5bacb-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5bacb-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="5bacb-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="5bacb-112">Область для содержимого.</span><span class="sxs-lookup"><span data-stu-id="5bacb-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="5bacb-113">Состояния NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="5bacb-113">NavigationWindow States</span></span>  
 <span data-ttu-id="5bacb-114">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="5bacb-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="5bacb-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="5bacb-115">VisualState Name</span></span>|<span data-ttu-id="5bacb-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5bacb-116">VisualStateGroup Name</span></span>|<span data-ttu-id="5bacb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5bacb-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5bacb-118">Valid</span><span class="sxs-lookup"><span data-stu-id="5bacb-118">Valid</span></span>|<span data-ttu-id="5bacb-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bacb-119">ValidationStates</span></span>|<span data-ttu-id="5bacb-120">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="5bacb-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5bacb-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5bacb-121">InvalidFocused</span></span>|<span data-ttu-id="5bacb-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bacb-122">ValidationStates</span></span>|<span data-ttu-id="5bacb-123">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="5bacb-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5bacb-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5bacb-124">InvalidUnfocused</span></span>|<span data-ttu-id="5bacb-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bacb-125">ValidationStates</span></span>|<span data-ttu-id="5bacb-126">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="5bacb-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="5bacb-127">Пример ControlTemplate NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="5bacb-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="5bacb-128">Несмотря на то, что этот пример содержит все элементы, определенные в <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Navigation.NavigationWindow> по умолчанию, конкретные значения следует рассматривать как примеры.</span><span class="sxs-lookup"><span data-stu-id="5bacb-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="5bacb-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5bacb-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5bacb-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5bacb-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bacb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="5bacb-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5bacb-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="5bacb-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5bacb-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="5bacb-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5bacb-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="5bacb-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5bacb-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5bacb-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
