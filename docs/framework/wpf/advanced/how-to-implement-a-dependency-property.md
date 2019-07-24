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
# <a name="how-to-implement-a-dependency-property"></a>Практическое руководство. Реализация свойства зависимостей
В этом примере показано, как выполнить обратное создание свойства среды CLR с <xref:System.Windows.DependencyProperty> полем, определив таким образом свойство зависимостей. Если вы определяете собственные свойства и хотите, чтобы они поддерживали множество аспектов функциональности [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], включая стили, привязку данных, наследование, анимацию и значения по умолчанию, следует реализовать их как свойства зависимостей.  
  
## <a name="example"></a>Пример  
 В следующем примере сначала регистрируется свойство зависимости путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метода. Имя поля идентификатора, используемого для хранения имени и характеристик свойства зависимостей, должно быть <xref:System.Windows.DependencyProperty.Name%2A> выбрано для свойства зависимостей в рамках <xref:System.Windows.DependencyProperty.Register%2A> вызова, к которому добавляется строка `Property`литерала. Например, если зарегистрировать свойство зависимостей с помощью <xref:System.Windows.DependencyProperty.Name%2A> объекта `Location`, то поле идентификатора, определяемое для свойства зависимостей, должно иметь имя `LocationProperty`.  
  
 В этом примере имя свойства зависимостей и его метод `State`доступа CLR имеет значение; поле идентификатора имеет `StateProperty`значение; тип свойства — <xref:System.Boolean>, а тип, регистрирующий свойство зависимостей, — `MyStateControl`.  
  
 Если не следовать этому шаблону именования, конструкторы могут неправильно обработать свойство и определенные аспекты применения стиля в системе свойств могут работать не так, как ожидалось.  
  
 Для свойства зависимости можно также указать используемые по умолчанию метаданные. В этом примере в качестве значения по умолчанию для свойства зависимости `State` регистрируется значение `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Дополнительные сведения о том, как и Зачем реализовывать свойство зависимостей, в отличие от простого резервного копирования свойства CLR с закрытым полем, см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Разделы практического руководства](properties-how-to-topics.md)
