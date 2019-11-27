---
title: Стили и шаблоны элемента Window
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 01233c5d0179e1a6f9bed651cd1f18058bfac168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283603"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="4bedd-102">Стили и шаблоны элемента Window</span><span class="sxs-lookup"><span data-stu-id="4bedd-102">Window Styles and Templates</span></span>
<span data-ttu-id="4bedd-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="4bedd-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="4bedd-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4bedd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4bedd-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="4bedd-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="4bedd-106">Части окна</span><span class="sxs-lookup"><span data-stu-id="4bedd-106">Window Parts</span></span>  
 <span data-ttu-id="4bedd-107">Элемент управления <xref:System.Windows.Window> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="4bedd-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="4bedd-108">Состояния окна</span><span class="sxs-lookup"><span data-stu-id="4bedd-108">Window States</span></span>  
 <span data-ttu-id="4bedd-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="4bedd-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="4bedd-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="4bedd-110">VisualState Name</span></span>|<span data-ttu-id="4bedd-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4bedd-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4bedd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4bedd-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4bedd-113">Допустимо</span><span class="sxs-lookup"><span data-stu-id="4bedd-113">Valid</span></span>|<span data-ttu-id="4bedd-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4bedd-114">ValidationStates</span></span>|<span data-ttu-id="4bedd-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="4bedd-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4bedd-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4bedd-116">InvalidFocused</span></span>|<span data-ttu-id="4bedd-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4bedd-117">ValidationStates</span></span>|<span data-ttu-id="4bedd-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="4bedd-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4bedd-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4bedd-119">InvalidUnfocused</span></span>|<span data-ttu-id="4bedd-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4bedd-120">ValidationStates</span></span>|<span data-ttu-id="4bedd-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="4bedd-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="4bedd-122">Пример для ControlTemplate окна</span><span class="sxs-lookup"><span data-stu-id="4bedd-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="4bedd-123">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="4bedd-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="4bedd-124"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4bedd-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4bedd-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4bedd-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bedd-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bedd-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4bedd-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="4bedd-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4bedd-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="4bedd-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4bedd-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="4bedd-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4bedd-130">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="4bedd-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
