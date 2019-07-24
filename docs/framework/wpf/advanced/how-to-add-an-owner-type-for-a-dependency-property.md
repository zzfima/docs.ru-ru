---
title: Практическое руководство. Добавление типа владельца для свойства зависимостей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401129"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="c6f77-102">Практическое руководство. Добавление типа владельца для свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="c6f77-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="c6f77-103">В этом примере показано, как добавить класс в качестве владельца свойства зависимостей, зарегистрированного для другого типа.</span><span class="sxs-lookup"><span data-stu-id="c6f77-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="c6f77-104">Таким образом, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] читатель и система свойств могут распознать класс как дополнительный владелец свойства.</span><span class="sxs-lookup"><span data-stu-id="c6f77-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="c6f77-105">Добавление в качестве владельца (необязательно) позволяет добавить класс для предоставления метаданных конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="c6f77-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="c6f77-106">В следующем примере — это `StateProperty` свойство, зарегистрированное `MyStateControl` классом.</span><span class="sxs-lookup"><span data-stu-id="c6f77-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="c6f77-107">Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью <xref:System.Windows.DependencyProperty.AddOwner%2A> метода, в частности с помощью сигнатуры, которая позволяет использовать новые метаданные для свойства зависимостей в том виде, в котором оно существует в добавлении типа.</span><span class="sxs-lookup"><span data-stu-id="c6f77-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="c6f77-108">Обратите внимание, что необходимо предоставить методы доступа среды CLR для свойства, аналогичные примеру, приведенному в примере [реализации свойства зависимостей](how-to-implement-a-dependency-property.md) , а также повторно предоставлять идентификатор свойства зависимости для класса, добавляемого в качестве владельца.</span><span class="sxs-lookup"><span data-stu-id="c6f77-108">Notice that you should provide common language runtime (CLR) accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="c6f77-109">Без оболочек свойство зависимости по-прежнему будет работать с точки зрения программного доступа с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6f77-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="c6f77-110">Но обычно требуется параллельное поведение системы свойств с оболочками свойств CLR.</span><span class="sxs-lookup"><span data-stu-id="c6f77-110">But you typically want to parallel this property-system behavior with the CLR property wrappers.</span></span> <span data-ttu-id="c6f77-111">Оболочки упрощают задание свойства зависимостей программным способом и позволяют задавать свойства в качестве [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c6f77-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="c6f77-112">Чтобы узнать, как переопределить метаданные по умолчанию, см. раздел [Переопределение метаданных для свойства зависимостей](how-to-override-metadata-for-a-dependency-property.md).</span><span class="sxs-lookup"><span data-stu-id="c6f77-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6f77-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c6f77-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="c6f77-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6f77-114">See also</span></span>

- [<span data-ttu-id="c6f77-115">Пользовательские свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="c6f77-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="c6f77-116">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="c6f77-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
