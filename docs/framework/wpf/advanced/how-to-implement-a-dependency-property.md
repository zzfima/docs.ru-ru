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
ms.openlocfilehash: 6f2fb9b0824feb6253527de063f58da2427d0c06
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400354"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="721fb-102">Практическое руководство. Реализация свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="721fb-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="721fb-103">В этом примере показано, как выполнить обратное создание свойства среды CLR с <xref:System.Windows.DependencyProperty> полем, определив таким образом свойство зависимостей.</span><span class="sxs-lookup"><span data-stu-id="721fb-103">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="721fb-104">Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="721fb-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="721fb-105">Пример</span><span class="sxs-lookup"><span data-stu-id="721fb-105">Example</span></span>  
 <span data-ttu-id="721fb-106">В следующем примере сначала регистрируется свойство зависимости путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="721fb-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="721fb-107">Имя поля идентификатора, используемого для хранения имени и характеристик свойства зависимостей, должно быть <xref:System.Windows.DependencyProperty.Name%2A> выбрано для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, к которому добавляется строка `Property`литерала.</span><span class="sxs-lookup"><span data-stu-id="721fb-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="721fb-108">Например, если зарегистрировать свойство зависимостей с помощью <xref:System.Windows.DependencyProperty.Name%2A> объекта `Location`, то поле идентификатора, определяемое для свойства зависимостей, должно иметь имя `LocationProperty`.</span><span class="sxs-lookup"><span data-stu-id="721fb-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="721fb-109">В этом примере имя свойства зависимостей и его метод `State`доступа CLR имеет значение; поле идентификатора имеет `StateProperty`значение; тип свойства — <xref:System.Boolean>, а тип, регистрирующий свойство зависимостей, — `MyStateControl`.</span><span class="sxs-lookup"><span data-stu-id="721fb-109">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="721fb-110">Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="721fb-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="721fb-111">Для свойства зависимости можно также указать используемые по умолчанию метаданные.</span><span class="sxs-lookup"><span data-stu-id="721fb-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="721fb-112">В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="721fb-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="721fb-113">Дополнительные сведения о том, как и Зачем реализовывать свойство зависимостей, в отличие от простого резервного копирования свойства CLR с закрытым полем, см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="721fb-113">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721fb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="721fb-114">See also</span></span>

- [<span data-ttu-id="721fb-115">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="721fb-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="721fb-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="721fb-116">How-to Topics</span></span>](properties-how-to-topics.md)
