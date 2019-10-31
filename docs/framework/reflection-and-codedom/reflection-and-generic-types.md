---
title: Отражение и универсальные типы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
ms.openlocfilehash: b4d36cb04494b01f8864ec36639ab33339d4b087
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130086"
---
# <a name="reflection-and-generic-types"></a>Отражение и универсальные типы
<a name="top"></a> С точки зрения отражения различие между универсальным типом и обычным заключается в том, что с универсальным типом связан набор параметров типа (если это определение универсального типа) или аргументы типа (если это сконструированный тип). Универсальный метод отличается от обычного тем же.  
  
 Существует два важных аспекта, необходимых, чтобы понять, как отражение обрабатывает универсальные типы и методы.  
  
- Параметры типа определений универсальных типов и определений универсальных методов представлены экземплярами класса <xref:System.Type> .  
  
    > [!NOTE]
    > Многие свойства и методы класса <xref:System.Type> функционируют иначе, если объект <xref:System.Type> представляет параметр универсального типа. Эти различия описаны в разделах, посвященных этим свойствам и методам. Например, см. класс <xref:System.Type.IsAutoClass%2A> и тип <xref:System.Type.DeclaringType%2A>. Кроме того, некоторые элементы действительны, только если объект <xref:System.Type> представляет параметр универсального типа. Пример см. в разделе <xref:System.Type.GetGenericTypeDefinition%2A>.  
  
- Если экземпляр типа <xref:System.Type> представляет универсальный тип, он содержит массив типов, которые представляют параметры типа (для определений универсального типа) или аргументы типа (для сконструированных типов). То же самое справедливо для экземпляра класса <xref:System.Reflection.MethodInfo> , который представляет универсальный метод.  
  
 Отражение предоставляет методы <xref:System.Type> и <xref:System.Reflection.MethodInfo>, которые позволяют получить доступ к массиву параметров типа и определить, представляет ли экземпляр <xref:System.Type> параметр типа или фактический тип.  
  
 Пример кода, демонстрирующий описанные здесь методы, см. в статье [Практическое руководство. Изучение универсальных типов и создание их экземпляров с помощью отражения](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 В следующем обсуждении предполагается, что вы знакомы с терминологией универсальности, то есть понимаете различия между параметрами типа и аргументами, а также открытыми и закрытыми сконструированными типами. Дополнительные сведения см. в статье [Универсальные шаблоны](../../standard/generics/index.md).  
  
 Этот обзор состоит из следующих разделов.  
  
- [Это универсальный тип или метод?](#is_this_a_generic_type_or_method)  
  
- [Создание закрытых универсальных типов](#generating_closed_generic_types)  
  
- [Изучение аргументов типа и параметров типа](#examining_type_arguments)  
  
- [Инварианты](#invariants)  
  
- [См. также](#related_topics)  
  
<a name="is_this_a_generic_type_or_method"></a>   
## <a name="is-this-a-generic-type-or-method"></a>Это универсальный тип или метод?  
 При использовании отражения для изучения неизвестного типа, представленного экземпляром <xref:System.Type>, используйте свойство <xref:System.Type.IsGenericType%2A> , чтобы определить, является ли неизвестный тип универсальным. Возвращается значение `true` , если тип является универсальным. Аналогично при рассмотрении неизвестного метода, представленного экземпляром класса <xref:System.Reflection.MethodInfo> , воспользуйтесь свойством <xref:System.Reflection.MethodBase.IsGenericMethod%2A> , чтобы установить, является ли метод универсальным.  
  
### <a name="is-this-a-generic-type-or-method-definition"></a>Это определение универсального типа или метода?  
 Используйте свойство <xref:System.Type.IsGenericTypeDefinition%2A> , чтобы установить, представляет ли объект <xref:System.Type> определение универсального типа. Используйте метод <xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A> , чтобы определить, представляет ли <xref:System.Reflection.MethodInfo> определение универсального метода.  
  
 Определения универсальных типов и методов — это шаблоны, из которых создаются типы с возможностью создания экземпляров. Универсальные типы в библиотеке классов .NET Framework, такие как <xref:System.Collections.Generic.Dictionary%602>, являются определениями универсальных типов.  
  
### <a name="is-the-type-or-method-open-or-closed"></a>Является ли тип или метод открытым или закрытым?  
 Универсальный тип или метод является закрытым, если все его параметры типов были заменены типами с возможностью создания экземпляров, включая все параметры всех содержащихся типов. Создать экземпляр универсального типа можно лишь в том случае, если он закрыт. Свойство <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> возвращает значение `true` , если тип открыт. Для методов метод <xref:System.Reflection.MethodBase.ContainsGenericParameters%2A?displayProperty=nameWithType> выполняет ту же функцию.  
  
 [К началу](#top)  
  
<a name="generating_closed_generic_types"></a>   
## <a name="generating-closed-generic-types"></a>Создание закрытых универсальных типов  
 Получив определение универсального типа или метода, воспользуйтесь методом <xref:System.Type.MakeGenericType%2A> для создания закрытого универсального типа или методом <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> для создания <xref:System.Reflection.MethodInfo> для закрытого универсального метода.  
  
### <a name="getting-the-generic-type-or-method-definition"></a>Получение определения универсального типа или метода  
 При наличии открытого универсального типа или метода, который не является определением универсального типа или метода, невозможно создать его экземпляры и предоставить отсутствующие параметры типа. Необходимо иметь определение универсального типа или метода. Используйте метод <xref:System.Type.GetGenericTypeDefinition%2A> для получения определения универсального типа или метод <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> для получения определения универсального метода.  
  
 Например, если имеется объект <xref:System.Type> , представляющий `Dictionary<int, string>` (`Dictionary(Of Integer, String)` в Visual Basic) и требуется создать тип `Dictionary<string, MyClass>`, можно использовать метод <xref:System.Type.GetGenericTypeDefinition%2A> для получения объекта <xref:System.Type> , который представляет `Dictionary<TKey, TValue>` , а затем использовать метод <xref:System.Type.MakeGenericType%2A> для создания типа <xref:System.Type> , который представляет `Dictionary<int, MyClass>`.  
  
 Пример открытого универсального типа, который не является универсальным типом, см. в подразделе «Параметр типа и аргумент типа» далее в этом разделе.  
  
 [К началу](#top)  
  
<a name="examining_type_arguments"></a>   
## <a name="examining-type-arguments-and-type-parameters"></a>Изучение аргументов типа и параметров типа  
 Используйте метод <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> , чтобы получить массив объектов <xref:System.Type> , которые представляют параметры типа или аргументы типа для универсального типа; используйте метод <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> , чтобы выполнить то же самое для универсального метода.  
  
 Если известно, что объект <xref:System.Type> представляет параметр типа, отражение может ответить на множество дополнительных вопросов. Можно определить источник параметра типа, его местоположение и ограничения.  
  
### <a name="type-parameter-or-type-argument"></a>Параметр типа и аргумент типа  
 Чтобы определить, является ли конкретный элемент массива параметром типа или аргументом типа, используйте свойство <xref:System.Type.IsGenericParameter%2A> . Свойство <xref:System.Type.IsGenericParameter%2A> имеет значение `true` , если элемент является параметром типа.  
  
 Универсальный тип может быть открытым, не являясь определением универсального типа. В этом случае он содержит как аргументы типа, так и параметры типа. Например, в следующем коде класс `D` является производным от типа, созданного путем замены первого параметра типа класса `D` вторым параметром типа `B`.  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 При получении объекта <xref:System.Type> , представляющего `D<V, W>` , воспользуйтесь свойством <xref:System.Type.BaseType%2A> , чтобы получить его базовый тип. Полученный тип `type B<int, V>` будет открытым, но не будет являться определением универсального типа.  
  
### <a name="source-of-a-generic-parameter"></a>Источник универсального параметра  
 Параметр универсального типа может происходить от рассматриваемого типа, вмещающего типа или универсального метода. Определить источник параметра универсального типа можно следующим образом.  
  
- Во-первых, используйте свойство <xref:System.Type.DeclaringMethod%2A> , чтобы определить, является ли параметр типа производным от универсального метода. Если значение свойства не является пустой ссылкой (`Nothing` в Visual Basic), источник — универсальный метод.  
  
- Если источник не является универсальным методом, используйте свойство <xref:System.Type.DeclaringType%2A> , чтобы определить универсальный тип, к которому относится параметр универсального типа.  
  
 Если параметр типа относится к универсальному методу, свойство <xref:System.Type.DeclaringType%2A> возвращает тип, объявивший универсальный метод, что не имеет смысла.  
  
### <a name="position-of-a-generic-parameter"></a>Положение универсального параметра  
 В редких случаях бывает необходимо определить положение параметра типа в списке параметров типа его объявляющего класса. Допустим, имеется объект <xref:System.Type> , представляющий тип `B<int, V>` из предыдущего примера. Метод <xref:System.Type.GetGenericArguments%2A> предоставляет список аргументов типа, и при рассмотрении `V` можно воспользоваться свойствами <xref:System.Type.DeclaringMethod%2A> и <xref:System.Type.DeclaringType%2A> , чтобы установить его источник. Затем можно использовать свойство <xref:System.Type.GenericParameterPosition%2A> , чтобы определить его положение в списке параметров типа, в котором он был определен. В этом примере `V` находится в положении 0 (ноль) в списке параметров типа, где он был определен.  
  
### <a name="base-type-and-interface-constraints"></a>Ограничения базового типа и интерфейса  
 Используйте метод <xref:System.Type.GetGenericParameterConstraints%2A> для получения ограничений базового типа и ограничений интерфейса параметра типа. Порядок элементов массива не имеет значения. Элемент представляет ограничение интерфейса, если является типом интерфейса.  
  
### <a name="generic-parameter-attributes"></a>Атрибуты универсального параметра  
 Свойство <xref:System.Type.GenericParameterAttributes%2A> получает значение <xref:System.Reflection.GenericParameterAttributes> , которое указывает на дисперсию (ковариация и контрвариация) и особые ограничения параметра типа.  
  
#### <a name="covariance-and-contravariance"></a>Ковариация и контрвариация  
 Чтобы определить, является ли параметр типа ковариантным или контравариантным, примените маску <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> к значению <xref:System.Reflection.GenericParameterAttributes> , возвращаемому свойством <xref:System.Type.GenericParameterAttributes%2A> . Если результатом является <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, параметр типа является инвариантным. См. раздел [Ковариация и контрвариация](../../standard/generics/covariance-and-contravariance.md).  
  
#### <a name="special-constraints"></a>Особые ограничения  
 Чтобы определить особые ограничения параметра типа, примените маску <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> к значению <xref:System.Reflection.GenericParameterAttributes> , возвращаемому свойством <xref:System.Type.GenericParameterAttributes%2A> . Если результатом является <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, специальные ограничения отсутствуют. Параметр типа может быть ограничен ссылочным типом, являться типом значения, не допускающим значения NULL, и иметь конструктор без параметров.  
  
 [К началу](#top)  
  
<a name="invariants"></a>   
## <a name="invariants"></a>Инварианты  
 Таблицу неизменяемых условий для общих терминов отражения универсальных типов см. в разделе <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>. Дополнительные термины, связанные с универсальными методами, см. в разделе <xref:System.Reflection.MethodBase.IsGenericMethod%2A?displayProperty=nameWithType>.  
  
 [К началу](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Практическое руководство. Изучение универсальных типов и создание их экземпляров с помощью отражения](how-to-examine-and-instantiate-generic-types-with-reflection.md)|Показано использование свойств и методов <xref:System.Type> и <xref:System.Reflection.MethodInfo> для изучения универсальных типов.|  
|[Универсальные шаблоны](../../standard/generics/index.md)|Описана универсальность и поддержка этой технологии в .NET Framework.|  
|[Практическое руководство. Определение универсального типа с порождаемым отражением](how-to-define-a-generic-type-with-reflection-emit.md)|Показано использование порождения отражения для создания универсальных типов в динамических сборках.|  
|[Просмотр сведений о типах](viewing-type-information.md)|Описывается класс <xref:System.Type> и приводятся примеры кода, иллюстрирующие использование <xref:System.Type> с несколькими классами отражения для получения информации о конструкторах, методах, полях, свойствах и событиях.|
