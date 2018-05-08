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
ms.openlocfilehash: b0c5b33d841f43249f9559bd31f1ef8fe66ff05e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-a-dependency-property"></a>Практическое руководство. Реализация свойства зависимостей
В этом примере показано, как выполнить [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] свойство с <xref:System.Windows.DependencyProperty> поля, определяя таким свойством зависимостей. Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.  
  
## <a name="example"></a>Пример  
 В следующем примере сначала регистрируется свойство зависимостей, вызвав <xref:System.Windows.DependencyProperty.Register%2A> метод. Поле идентификатора, которое используется для хранения имени и характеристики свойства зависимостей, должно быть имя <xref:System.Windows.DependencyProperty.Name%2A> выбранным для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, добавлены в строковый литерал `Property`. Например если регистрируется свойство зависимостей с <xref:System.Windows.DependencyProperty.Name%2A> из `Location`, поле идентификатора, определяемое для свойства зависимостей необходимо присвоить имя `LocationProperty`.  
  
 В этом примере имя свойства зависимостей и его [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] метод доступа `State`; поле идентификатора `StateProperty`; тип свойства — <xref:System.Boolean>; и тип, который регистрирует свойство зависимости является `MyStateControl`.  
  
 Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.  
  
 Для свойства зависимости можно также указать используемые по умолчанию метаданные. В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Дополнительные сведения о том, как и зачем реализовывать свойство зависимости вместо предоставления закрытого поля для свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
