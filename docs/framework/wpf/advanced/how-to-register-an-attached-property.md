---
title: Как выполнить Регистрация вложенного свойства зависимостей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 71b516a1d181c409fef397b7c959860d47d05b37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608564"
---
# <a name="how-to-register-an-attached-property"></a>Как выполнить Регистрация вложенного свойства зависимостей
В этом примере демонстрируется регистрация присоединенного свойства и предоставление открытых методов доступа для использования свойства в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и в коде. Присоединенные свойства являются понятием синтаксиса, определенным в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Большинство присоединенных свойств для типов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также реализовано как свойства зависимостей. Свойства зависимостей можно использовать на любом <xref:System.Windows.DependencyObject> типов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как зарегистрировать присоединенное свойство как свойство зависимостей, с помощью <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод. Класс поставщика имеет возможность предоставления метаданных по умолчанию для свойства, применяемых в случае, когда свойство используется в другом классе и этот класс не переопределяет метаданные. В этом примере значение по умолчанию свойства `IsBubbleSource` равно `false`.  
  
 Класс поставщика для присоединенного свойства (даже если оно не зарегистрировано как свойство зависимостей) должен предоставлять статические методы доступа get и set, соответствующие правилам именования `Set`*[имя_присоединенного_свойства]* и `Get`*[имя_присоединенного_свойства]*. Эти методы доступа требуются для того, чтобы действующее средство чтения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознало свойство как атрибут в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и разрешило соответствующие типы.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.DependencyProperty>
- [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
