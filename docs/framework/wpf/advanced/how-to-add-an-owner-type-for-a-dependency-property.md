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
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Практическое руководство. Добавление типа владельца для свойства зависимостей
В этом примере показано, как добавить класс в качестве владельца свойства зависимостей, зарегистрированного для другого типа. Таким образом, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] читатель и система свойств могут распознать класс как дополнительный владелец свойства. Добавление в качестве владельца (необязательно) позволяет добавить класс для предоставления метаданных конкретного типа.  
  
 В следующем примере — это `StateProperty` свойство, зарегистрированное `MyStateControl` классом. Класс `UnrelatedStateControl` добавляет себя в качестве владельца `StateProperty` с помощью <xref:System.Windows.DependencyProperty.AddOwner%2A> метода, в частности с помощью сигнатуры, которая позволяет использовать новые метаданные для свойства зависимостей в том виде, в котором оно существует в добавлении типа. Обратите внимание, что необходимо предоставить методы доступа среды CLR для свойства, аналогичные примеру, приведенному в примере [реализации свойства зависимостей](how-to-implement-a-dependency-property.md) , а также повторно предоставлять идентификатор свойства зависимости для класса, добавляемого в качестве владельца.  
  
 Без оболочек свойство зависимости по-прежнему будет работать с точки зрения программного доступа с помощью <xref:System.Windows.DependencyObject.GetValue%2A> или <xref:System.Windows.DependencyObject.SetValue%2A>. Но обычно требуется параллельное поведение системы свойств с оболочками свойств CLR. Оболочки упрощают задание свойства зависимостей программным способом и позволяют задавать свойства в качестве [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибутов.  
  
 Чтобы узнать, как переопределить метаданные по умолчанию, см. раздел [Переопределение метаданных для свойства зависимостей](how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>См. также

- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
