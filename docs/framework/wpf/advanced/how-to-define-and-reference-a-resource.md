---
title: "Практическое руководство. Определение и создание ссылки на ресурс"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="96b46-102">Практическое руководство. Определение и создание ссылки на ресурс</span><span class="sxs-lookup"><span data-stu-id="96b46-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="96b46-103">В этом примере показано, как определить ресурс и ссылки на него с помощью атрибута в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b46-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="96b46-104">Пример</span><span class="sxs-lookup"><span data-stu-id="96b46-104">Example</span></span>  
 <span data-ttu-id="96b46-105">В следующем примере определяются два типа ресурсов: <xref:System.Windows.Media.SolidColorBrush> ресурсов, а также несколько <xref:System.Windows.Style> ресурсов.</span><span class="sxs-lookup"><span data-stu-id="96b46-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="96b46-106"><xref:System.Windows.Media.SolidColorBrush> Ресурсов `MyBrush` используется для предоставления значений нескольких свойств, каждый из которых принимает <xref:System.Windows.Media.Brush> введите значение.</span><span class="sxs-lookup"><span data-stu-id="96b46-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="96b46-107"><xref:System.Windows.Style> Ресурсов `PageBackground`, `TitleText` и `Label` каждый целевой определенного типа элемента управления.</span><span class="sxs-lookup"><span data-stu-id="96b46-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="96b46-108">Стили устанавливается ряд различных свойств для целевых элементов, если ресурс стиля ссылается ключ ресурса и используется для задания <xref:System.Windows.FrameworkElement.Style%2A> свойства нескольких элементов конкретного элемента управления, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b46-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="96b46-109">Примечание, что одно из свойств метода установки `Label` также ссылается на стиль `MyBrush` ресурсов, определенные ранее.</span><span class="sxs-lookup"><span data-stu-id="96b46-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="96b46-110">Это распространенный способ, но важно запомнить синтаксический анализ и введенные в словаре ресурсов, в том порядке, приведенном ресурсов.</span><span class="sxs-lookup"><span data-stu-id="96b46-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="96b46-111">Запрос ресурсов также осуществляется в порядке найдены в словаре, если вы используете [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) чтобы ссылаться на них из другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="96b46-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="96b46-112">Убедитесь, что любой ресурс, на которую ссылается, определены в коллекции ресурсов, до которой затем запрошена этого ресурса.</span><span class="sxs-lookup"><span data-stu-id="96b46-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="96b46-113">При необходимости можно обойти строгий порядок создания ресурсов с помощью [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) вместо этого ссылок во время выполнения, но следует иметь в виду, это DynamicResource метод окажет влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="96b46-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="96b46-114">Дополнительные сведения см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="96b46-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="96b46-115">См. также</span><span class="sxs-lookup"><span data-stu-id="96b46-115">See Also</span></span>  
 [<span data-ttu-id="96b46-116">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="96b46-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="96b46-117">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="96b46-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
