---
title: Практическое руководство. Реализация свойства зависимостей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: e2f18cb3941be2ebf4315a844c05b91ff49c6aa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223805"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="11b15-102">Практическое руководство. Реализация свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="11b15-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="11b15-103">В этом примере показано, как создавать резервные [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] свойство с <xref:System.Windows.DependencyProperty> поля, определив тем самым свойство зависимости.</span><span class="sxs-lookup"><span data-stu-id="11b15-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="11b15-104">Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="11b15-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11b15-105">Пример</span><span class="sxs-lookup"><span data-stu-id="11b15-105">Example</span></span>  
 <span data-ttu-id="11b15-106">В следующем примере сначала регистрируется свойство зависимости путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="11b15-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="11b15-107">Поле идентификатора, которое используется для хранения имени и характеристик свойства зависимости должно быть имя <xref:System.Windows.DependencyProperty.Name%2A> вы выбрали для свойства зависимостей, как часть <xref:System.Windows.DependencyProperty.Register%2A> вызова, добавлением строковый литерал `Property`.</span><span class="sxs-lookup"><span data-stu-id="11b15-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="11b15-108">Например при регистрации свойства зависимостей с <xref:System.Windows.DependencyProperty.Name%2A> из `Location`, то поле идентификатора, определяемое для свойства зависимостей должны именоваться `LocationProperty`.</span><span class="sxs-lookup"><span data-stu-id="11b15-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="11b15-109">В этом примере имя свойства зависимостей и его [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] метод доступа является `State`; поле идентификатора называется `StateProperty`; тип свойства — <xref:System.Boolean>; и тип, регистрирующий свойство зависимостей является `MyStateControl`.</span><span class="sxs-lookup"><span data-stu-id="11b15-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="11b15-110">Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="11b15-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="11b15-111">Для свойства зависимости можно также указать используемые по умолчанию метаданные.</span><span class="sxs-lookup"><span data-stu-id="11b15-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="11b15-112">В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="11b15-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="11b15-113">Дополнительные сведения о том, как и зачем реализовывать свойство зависимости вместо предоставления закрытого поля для свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], см. в разделе [Общие сведения о свойствах зависимости](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11b15-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b15-114">См. также</span><span class="sxs-lookup"><span data-stu-id="11b15-114">See also</span></span>

- [<span data-ttu-id="11b15-115">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="11b15-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="11b15-116">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="11b15-116">How-to Topics</span></span>](properties-how-to-topics.md)
