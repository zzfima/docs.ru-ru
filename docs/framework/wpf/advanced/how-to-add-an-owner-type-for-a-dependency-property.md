---
title: "Практическое руководство. Добавление типа владельца для свойства зависимости"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93934c8f84a7257445b530e27896342bdd73aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="9995e-102">Практическое руководство. Добавление типа владельца для свойства зависимости</span><span class="sxs-lookup"><span data-stu-id="9995e-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="9995e-103">В этом примере показано, как добавить класс в качестве владельца свойства зависимостей, зарегистрированного для другого типа.</span><span class="sxs-lookup"><span data-stu-id="9995e-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="9995e-104">Таким образом, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] чтения и система свойств способны распознать класс в качестве дополнительного владельца свойства.</span><span class="sxs-lookup"><span data-stu-id="9995e-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="9995e-105">Добавление в качестве владельца при необходимости позволяет добавлять класс для предоставления метаданных определенного типа.</span><span class="sxs-lookup"><span data-stu-id="9995e-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="9995e-106">В следующем примере `StateProperty` является свойством, зарегистрированным `MyStateControl` класса.</span><span class="sxs-lookup"><span data-stu-id="9995e-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="9995e-107">Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью <xref:System.Windows.DependencyProperty.AddOwner%2A> метода, в частности, используя подпись, которая обеспечивает новые метаданные для свойства зависимостей, которое существует в добавленном типе.</span><span class="sxs-lookup"><span data-stu-id="9995e-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="9995e-108">Обратите внимание, что необходимо предоставить [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] методы доступа для свойства, как показано в примере [реализации свойства зависимостей,](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) пример, а также повторно предоставить идентификатор свойства зависимостей для класса, добавляемого в как владелец.</span><span class="sxs-lookup"><span data-stu-id="9995e-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="9995e-109">Без оболочки свойство зависимости по-прежнему будет работать с точки зрения программного доступа с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="9995e-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="9995e-110">Однако чаще всего требуется параллельное поведение системы свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] оболочек свойств.</span><span class="sxs-lookup"><span data-stu-id="9995e-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="9995e-111">Оболочки облегчают программным способом установите для свойства зависимостей и делают возможным установку свойств в качестве [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9995e-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="9995e-112">Чтобы узнать, как переопределить метаданные по умолчанию, в разделе [переопределения метаданных для свойства зависимостей](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span><span class="sxs-lookup"><span data-stu-id="9995e-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9995e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9995e-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="9995e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9995e-114">See Also</span></span>  
 [<span data-ttu-id="9995e-115">Пользовательские свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="9995e-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="9995e-116">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="9995e-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
