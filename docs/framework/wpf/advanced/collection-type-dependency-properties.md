---
title: Свойства зависимостей типа коллекция
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
ms.openlocfilehash: dd268c0c132f4ecefe7b2336432442d9569ca38f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401553"
---
# <a name="collection-type-dependency-properties"></a>Свойства зависимостей типа коллекция
Этот раздел содержит рекомендации и примеры шаблонов для реализации свойства зависимостей, где типом свойства является коллекция.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Реализация свойства зависимостей типа "коллекция"  
 Для свойства зависимостей в целом шаблон реализации, который вы выполняете, заключается в том, что вы определяете оболочку свойств CLR, где это свойство поддерживается <xref:System.Windows.DependencyProperty> идентификатором, а не полем или другой конструкцией. При реализации свойства типа "коллекция" вы следуете этому же шаблону. Однако свойство типа коллекции представляет некоторую сложность шаблона, когда тип, содержащийся в коллекции, сам <xref:System.Windows.DependencyObject> является производным классом или. <xref:System.Windows.Freezable>  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Инициализация коллекции за пределами значения по умолчанию  
 При создании свойства зависимостей вы не указываете значение свойства по умолчанию в качестве начального значения поля. Вместо этого значение по умолчанию указывается через метаданные свойства зависимостей. Если свойство является ссылочным типом, значение по умолчанию, заданное в метаданных свойства зависимостей, не является значением по умолчанию для каждого экземпляра. Напротив, это значение по умолчанию, которое применяется ко всем экземплярам типа. Поэтому необходимо избегать использования единственной статической коллекции, определенной метаданными свойства коллекции, в качестве рабочего значения по умолчанию для вновь создаваемых экземпляров типа. Вместо этого необходимо явно задать в качестве значения коллекции уникальную коллекцию (экземпляр) как часть логики конструктора класса. В противном случае будет создан случайный одноэлементный класс.  
  
 Рассмотрим следующий пример. В следующем разделе примера показано определение класса `Aquarium`. Класс определяет свойство `AquariumObjects`зависимости типа коллекции, которое использует универсальный <xref:System.Collections.Generic.List%601> тип с <xref:System.Windows.FrameworkElement> ограничением типа. В вызове свойства зависимостей метаданные устанавливают значение по умолчанию, чтобы быть новым универсальным <xref:System.Collections.Generic.List%601>. <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29>  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Однако если оставить такой код, как в примере, это значение по умолчанию одного списка будет использоваться совместно для всех экземпляров `Aquarium`. Если выполнить следующий тестовый код, предназначенный для демонстрации того, как создаются два отдельных экземпляра `Aquarium` и добавляется один отличный `Fish` для каждого из них, вы увидите странный результат.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Вместо того чтобы каждой коллекции назначалось число 1, каждой коллекции назначается число 2! Это происходит, поскольку каждый `Aquarium` добавил свой объект `Fish` в коллекцию значений по умолчанию, которая является результатом вызова одного конструктора в метаданных и, таким образом, совместно используется всеми экземплярами. Как правило, такая ситуация нежелательна.  
  
 Чтобы устранить эту проблему, необходимо сбросить значение свойства зависимостей коллекции, задав уникальный экземпляр в составе вызова конструктора класса. Поскольку свойство является свойством зависимостей только для чтения, для его <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> <xref:System.Windows.DependencyPropertyKey> установки используется метод, который доступен только в пределах класса.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Теперь, запустив тот же тестовый код еще раз, вы можете заметить, что результаты стали более ожидаемыми, то есть каждый `Aquarium` поддерживает свою собственную уникальную коллекцию.  
  
 Если свойство коллекции будет доступным для чтения и записи, в этот шаблон потребуется внести небольшое изменение. В этом случае можно вызвать открытый метод доступа set из конструктора, чтобы выполнить инициализацию, которая по-прежнему вызовет неключевую подпись <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> в рамках программы установки, используя открытый <xref:System.Windows.DependencyProperty> идентификатор.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Передача сведений об изменении значений привязки из свойств коллекции  
 Свойство коллекции, которое само является свойством зависимостей, не сообщает об изменениях своих подсвойств автоматически. При создании привязок в коллекции это может мешать привязке сообщать об изменениях и, следовательно, нарушить некоторые сценарии привязки данных. Однако, если тип <xref:System.Windows.FreezableCollection%601> коллекции используется в качестве типа коллекции, то все изменения подсвойств в содержащихся в коллекции элементах будут правильно отправлены, а привязка работает должным образом.  
  
 Чтобы включить привязку подсвойства в коллекции объектов зависимостей, создайте свойство коллекции как тип <xref:System.Windows.FreezableCollection%601>с ограничением типа для этой коллекции в любом <xref:System.Windows.DependencyObject> производном классе.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FreezableCollection%601>
- [Код XAML и пользовательские классы для WPF](xaml-and-custom-classes-for-wpf.md)
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
- [Метаданные свойства зависимостей](dependency-property-metadata.md)
