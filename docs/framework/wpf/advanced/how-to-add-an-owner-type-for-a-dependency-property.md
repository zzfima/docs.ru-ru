---
title: Как выполнить Добавление типа владельца для свойства зависимостей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 528ec28750c6ce7dffb1104d750679a546df0487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697066"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Как выполнить Добавление типа владельца для свойства зависимостей
В этом примере показано, как добавить класс в качестве владельца свойства зависимостей, зарегистрированные для другого типа. Таким образом, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] чтения и система свойств способны распознать класс в качестве дополнительного владельца свойства. Добавление в качестве владельца при необходимости позволяет добавлять класс для предоставления метаданных определенного типа.  
  
 В следующем примере `StateProperty` свойство регистрируется путем `MyStateControl` класса. Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью <xref:System.Windows.DependencyProperty.AddOwner%2A> метода, в частности с помощью подпись, которая обеспечивает более новые метаданные для свойства зависимостей, так как оно существует в типе добавление. Обратите внимание, что необходимо предоставить [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] методы доступа для свойства, как показано в примере [реализация свойства зависимостей](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) пример, а также повторно предоставить идентификатор свойства зависимостей для класса, добавляемого в как владелец.  
  
 Без оболочки свойства зависимостей по-прежнему будет работать с точки зрения программный доступ с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>. Но чаще всего требуется параллельное поведение системы свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] оболочек свойств. Оболочки упрощают установку свойства зависимости и обеспечить возможность задать свойства, как [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибуты.  
  
 Чтобы узнать, как переопределить метаданные по умолчанию, см. в разделе [переопределение метаданных для свойства зависимостей](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>См. также
- [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
