---
title: Стили и шаблоны элемента ContextMenu
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283542"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="a48c1-102">Стили и шаблоны элемента ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a48c1-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="a48c1-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="a48c1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="a48c1-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a48c1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a48c1-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="a48c1-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="a48c1-106">Части ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a48c1-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="a48c1-107">Элемент управления <xref:System.Windows.Controls.ContextMenu> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="a48c1-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="a48c1-108">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ContextMenu>шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в пределах <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="a48c1-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="a48c1-109">(<xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="a48c1-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="a48c1-110">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым дочерним элементом <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить <xref:System.Windows.Controls.ItemsPresenter> имя, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="a48c1-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="a48c1-111">Состояния ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a48c1-111">ContextMenu States</span></span>  
 <span data-ttu-id="a48c1-112">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="a48c1-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="a48c1-113">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="a48c1-113">VisualState Name</span></span>|<span data-ttu-id="a48c1-114">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a48c1-114">VisualStateGroup Name</span></span>|<span data-ttu-id="a48c1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a48c1-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a48c1-116">Valid</span><span class="sxs-lookup"><span data-stu-id="a48c1-116">Valid</span></span>|<span data-ttu-id="a48c1-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a48c1-117">ValidationStates</span></span>|<span data-ttu-id="a48c1-118">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="a48c1-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a48c1-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a48c1-119">InvalidFocused</span></span>|<span data-ttu-id="a48c1-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a48c1-120">ValidationStates</span></span>|<span data-ttu-id="a48c1-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a48c1-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a48c1-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a48c1-122">InvalidUnfocused</span></span>|<span data-ttu-id="a48c1-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a48c1-123">ValidationStates</span></span>|<span data-ttu-id="a48c1-124">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="a48c1-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="a48c1-125">Пример ControlTemplate "ContextMenu"</span><span class="sxs-lookup"><span data-stu-id="a48c1-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="a48c1-126">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="a48c1-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="a48c1-127">В <xref:System.Windows.Controls.ControlTemplate> используются следующие ресурсы.</span><span class="sxs-lookup"><span data-stu-id="a48c1-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a48c1-128">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a48c1-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48c1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a48c1-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a48c1-130">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="a48c1-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a48c1-131">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="a48c1-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a48c1-132">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="a48c1-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a48c1-133">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="a48c1-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
