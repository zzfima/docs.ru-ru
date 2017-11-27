---
title: "Практическое руководство. Реализация свойства зависимостей"
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
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bc4dee8f0b2eef76e5769ae7da3a13edf7c3300
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="d5a09-102">Практическое руководство. Реализация свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="d5a09-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="d5a09-103">В этом примере показано, как выполнить [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] свойство с <xref:System.Windows.DependencyProperty> поля, определяя таким свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d5a09-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="d5a09-104">Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d5a09-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5a09-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d5a09-105">Example</span></span>  
 <span data-ttu-id="d5a09-106">В следующем примере сначала регистрируется свойство зависимостей, вызвав <xref:System.Windows.DependencyProperty.Register%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d5a09-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="d5a09-107">Поле идентификатора, которое используется для хранения имени и характеристики свойства зависимостей, должно быть имя <xref:System.Windows.DependencyProperty.Name%2A> выбранным для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, добавлены в строковый литерал `Property`.</span><span class="sxs-lookup"><span data-stu-id="d5a09-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="d5a09-108">Например если регистрируется свойство зависимостей с <xref:System.Windows.DependencyProperty.Name%2A> из `Location`, поле идентификатора, определяемое для свойства зависимостей необходимо присвоить имя `LocationProperty`.</span><span class="sxs-lookup"><span data-stu-id="d5a09-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="d5a09-109">В этом примере имя свойства зависимостей и его [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] метод доступа `State`; поле идентификатора `StateProperty`; тип свойства — <xref:System.Boolean>; и тип, который регистрирует свойство зависимости является `MyStateControl`.</span><span class="sxs-lookup"><span data-stu-id="d5a09-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="d5a09-110">Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="d5a09-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="d5a09-111">Для свойства зависимости можно также указать используемые по умолчанию метаданные.</span><span class="sxs-lookup"><span data-stu-id="d5a09-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="d5a09-112">В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d5a09-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="d5a09-113">Дополнительные сведения о том, как и зачем реализовывать свойство зависимости вместо предоставления закрытого поля для свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5a09-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a09-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d5a09-114">See Also</span></span>  
 [<span data-ttu-id="d5a09-115">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="d5a09-115">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="d5a09-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d5a09-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
