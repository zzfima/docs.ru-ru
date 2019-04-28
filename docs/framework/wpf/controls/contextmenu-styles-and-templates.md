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
ms.openlocfilehash: 6650d5a7be8ebe8fc2dcd7af7c854da669de87f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912331"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="142ae-102">Стили и шаблоны элемента ContextMenu</span><span class="sxs-lookup"><span data-stu-id="142ae-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="142ae-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ContextMenu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="142ae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="142ae-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="142ae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="142ae-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="142ae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="142ae-106">Части ContextMenu</span><span class="sxs-lookup"><span data-stu-id="142ae-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="142ae-107"><xref:System.Windows.Controls.ContextMenu> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="142ae-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="142ae-108">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ContextMenu>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="142ae-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="142ae-109">( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> дает возможность прокрутки в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="142ae-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="142ae-110">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, необходимо предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="142ae-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="142ae-111">Состояния ContextMenu</span><span class="sxs-lookup"><span data-stu-id="142ae-111">ContextMenu States</span></span>  
 <span data-ttu-id="142ae-112">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ContextMenu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="142ae-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="142ae-113">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="142ae-113">VisualState Name</span></span>|<span data-ttu-id="142ae-114">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="142ae-114">VisualStateGroup Name</span></span>|<span data-ttu-id="142ae-115">Описание</span><span class="sxs-lookup"><span data-stu-id="142ae-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="142ae-116">Valid</span><span class="sxs-lookup"><span data-stu-id="142ae-116">Valid</span></span>|<span data-ttu-id="142ae-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="142ae-117">ValidationStates</span></span>|<span data-ttu-id="142ae-118">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="142ae-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="142ae-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="142ae-119">InvalidFocused</span></span>|<span data-ttu-id="142ae-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="142ae-120">ValidationStates</span></span>|<span data-ttu-id="142ae-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="142ae-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="142ae-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="142ae-122">InvalidUnfocused</span></span>|<span data-ttu-id="142ae-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="142ae-123">ValidationStates</span></span>|<span data-ttu-id="142ae-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="142ae-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="142ae-125">Пример шаблона элемента управления ContextMenu</span><span class="sxs-lookup"><span data-stu-id="142ae-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="142ae-126">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ContextMenu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="142ae-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="142ae-127"><xref:System.Windows.Controls.ControlTemplate> Использует следующие ресурсы.</span><span class="sxs-lookup"><span data-stu-id="142ae-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="142ae-128">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="142ae-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142ae-129">См. также</span><span class="sxs-lookup"><span data-stu-id="142ae-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="142ae-130">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="142ae-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="142ae-131">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="142ae-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="142ae-132">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="142ae-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="142ae-133">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="142ae-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
