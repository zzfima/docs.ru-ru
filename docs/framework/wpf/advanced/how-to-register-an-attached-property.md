---
title: Практическое руководство. Регистрация присоединенного свойства
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4c678a64b62b8f4db24cf39ffbafac52e56c9982
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768684"
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="ef902-102">Практическое руководство. Регистрация присоединенного свойства</span><span class="sxs-lookup"><span data-stu-id="ef902-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="ef902-103">В этом примере демонстрируется регистрация присоединенного свойства и предоставление открытых методов доступа для использования свойства в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и в коде.</span><span class="sxs-lookup"><span data-stu-id="ef902-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="ef902-104">Присоединенные свойства являются понятием синтаксиса, определенным в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef902-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ef902-105">Большинство присоединенных свойств для типов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также реализовано как свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ef902-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="ef902-106">Свойства зависимостей можно использовать на любом <xref:System.Windows.DependencyObject> типов.</span><span class="sxs-lookup"><span data-stu-id="ef902-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef902-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ef902-107">Example</span></span>  
 <span data-ttu-id="ef902-108">В следующем примере показано, как зарегистрировать присоединенное свойство как свойство зависимостей, с помощью <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ef902-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="ef902-109">Класс поставщика имеет возможность предоставления метаданных по умолчанию для свойства, применяемых в случае, когда свойство используется в другом классе и этот класс не переопределяет метаданные.</span><span class="sxs-lookup"><span data-stu-id="ef902-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="ef902-110">В этом примере значение по умолчанию свойства `IsBubbleSource` равно `false`.</span><span class="sxs-lookup"><span data-stu-id="ef902-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="ef902-111">Класс поставщика для присоединенного свойства (даже если оно не зарегистрировано как свойство зависимостей) должен предоставлять статические методы доступа get и set, соответствующие правилам именования `Set`*[имя_присоединенного_свойства]* и `Get`*[имя_присоединенного_свойства]*.</span><span class="sxs-lookup"><span data-stu-id="ef902-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="ef902-112">Эти методы доступа требуются для того, чтобы действующее средство чтения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознало свойство как атрибут в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и разрешило соответствующие типы.</span><span class="sxs-lookup"><span data-stu-id="ef902-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="ef902-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ef902-113">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="ef902-114">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="ef902-114">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="ef902-115">Пользовательские свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="ef902-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="ef902-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ef902-116">How-to Topics</span></span>](properties-how-to-topics.md)
