---
title: Стили и шаблоны элемента DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: ac1dc4f74a8e8f3ad2e84c6d50239ec827306c28
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283529"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="8a2ce-102">Стили и шаблоны элемента DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="8a2ce-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="8a2ce-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="8a2ce-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8a2ce-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="8a2ce-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="8a2ce-106">DocumentViewer части</span><span class="sxs-lookup"><span data-stu-id="8a2ce-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="8a2ce-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="8a2ce-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="8a2ce-108">Part</span></span>|<span data-ttu-id="8a2ce-109">Type</span><span class="sxs-lookup"><span data-stu-id="8a2ce-109">Type</span></span>|<span data-ttu-id="8a2ce-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8a2ce-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8a2ce-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="8a2ce-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="8a2ce-112">Область содержимого и прокрутки.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="8a2ce-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="8a2ce-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="8a2ce-114">Поле поиска в нижней части по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="8a2ce-115">Состояния DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="8a2ce-115">DocumentViewer States</span></span>  
 <span data-ttu-id="8a2ce-116">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="8a2ce-117">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="8a2ce-117">VisualState Name</span></span>|<span data-ttu-id="8a2ce-118">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8a2ce-118">VisualStateGroup Name</span></span>|<span data-ttu-id="8a2ce-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8a2ce-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8a2ce-120">Valid</span><span class="sxs-lookup"><span data-stu-id="8a2ce-120">Valid</span></span>|<span data-ttu-id="8a2ce-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8a2ce-121">ValidationStates</span></span>|<span data-ttu-id="8a2ce-122">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8a2ce-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8a2ce-123">InvalidFocused</span></span>|<span data-ttu-id="8a2ce-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8a2ce-124">ValidationStates</span></span>|<span data-ttu-id="8a2ce-125">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8a2ce-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8a2ce-126">InvalidUnfocused</span></span>|<span data-ttu-id="8a2ce-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8a2ce-127">ValidationStates</span></span>|<span data-ttu-id="8a2ce-128">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="8a2ce-129">Пример ControlTemplate DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="8a2ce-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="8a2ce-130">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="8a2ce-131">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8a2ce-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8a2ce-132">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8a2ce-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2ce-133">См. также</span><span class="sxs-lookup"><span data-stu-id="8a2ce-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8a2ce-134">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="8a2ce-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8a2ce-135">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="8a2ce-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8a2ce-136">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="8a2ce-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8a2ce-137">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="8a2ce-137">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
