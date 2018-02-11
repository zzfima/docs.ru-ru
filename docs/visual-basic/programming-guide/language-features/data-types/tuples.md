---
title: "Кортежи в Visual Basic"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a>Кортежи (Visual Basic)

Начиная с Visual Basic 2017 г., в языке Visual Basic предлагает встроенную поддержку кортежей, который делает создание кортежей и доступ к элементам проще кортежей. Кортеж — это структура данных недоступно, с определенным номером и последовательность значений. При создании экземпляра кортежа, следует определить, количество и тип данных каждого значения (или элемент). Например кортеж (или пары) состоит из двух элементов. Возможно, первый `Boolean` значение, а второй — `String`. Поскольку кортежей упростить процесс сохранения нескольких значений в одном объекте, они часто используются как упрощенный способ возвращать несколько значений из метода.

> [!IMPORTANT]
> Поддержка кортежа требует <xref:System.ValueTuple> типа. Если 4.7 .NET Framework не установлена, необходимо добавить пакет NuGet `System.ValueTuple`, который можно найти в коллекции NuGet. Без этого пакета может получить ошибку компиляции аналогично «Предопределенный тип «ValueTuple(Of,,,)» не определен и не импортирован.»

## <a name="instantiating-and-using-a-tuple"></a>Создание и использование кортежа

Создать кортеж, заключив его круглые скобки обмена мгновенными сообщениями значений с разделителями запятыми. Затем каждый из этих значений становится полем кортежа. Например, следующий код определяет triple (или кортежа 3) с помощью `Date` как значение его первого, `String` его вторым и `Boolean` как третьего.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

По умолчанию имя каждого поля в кортеж включает строку `Item` вместе с положением на основе одного поля в кортеже. Для 3-кортежа `Date` поле является `Item1`, `String` поле является `Item2`и `Boolean` поле является `Item3`. Следующий пример отображает значения полей кортежа, созданный в предыдущей строке кода

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Поля кортеж Visual Basic, чтения и записи; После создания экземпляра кортеж его значения можно изменить. Следующий пример изменяет две из трех полей кортежа, созданные в предыдущем примере и отображает результат.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Создание экземпляра и использование именованных кортежа

Вместо того чтобы использовать имена по умолчанию для полей кортежа, можно создать экземпляр *кортеж с именем* , назначив собственные имена элементов кортежа. Поля кортежа может осуществляться по именам и назначенный *или* , их имена по умолчанию. В следующем примере создается же кортеж 3 как ранее, за исключением того, что она явно указана первое поле `EventDate`, второй `Name`, а в третьем `IsHoliday`. Затем он отображает значения полей, изменяет их и отображает значения полей еще раз.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Имена элементов выводимых кортежа

Начиная с 15,3 Visual Basic, Visual Basic могут выводить имена элементов кортежа; необходимо назначить их явно. Выводимый кортежа имена полезны в тех случаях, когда инициализировать кортежа из набора переменных, и требуется имя элемента кортежа должен совпадать с именем переменной. 

В следующем примере создается `stateInfo` кортеж, содержащий три явно именованные элементы, `state`, `stateName`, и `capital`. Обратите внимание, что при именовании элементы, оператор инициализации кортежа просто назначает именованных элементов значения переменных таким же именем.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Поскольку элементы и переменные имеют то же имя, компилятор Visual Basic может определить имена полей, как показано в следующем примере.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Чтобы включить имена элементов interred кортеж, необходимо определить версии компилятора Visual Basic для использования в проекте Visual Basic (\*.vbproj) файла: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Кортежи как возвращаемые значения методов

Метод может возвращать только одно значение. Часто хотя вам бы хотелось вызов метода для возврата нескольких значений. Чтобы обойти это ограничение несколькими способами:

- Можно создать пользовательский класс или структуру, свойства или поля представляют значения, возвращаемого методом. Таким образом — это решение высокой плотности; необходимо определить пользовательский тип которого предназначен только для извлечения значений из вызова метода.

- Возвращает одно значение из метода и возврата оставшиеся значения, передавая их по ссылке в метод. Это включает в себя дополнительную нагрузку, связанную с создания экземпляра переменной и риски при перезаписи значение переменной, которая передается по ссылке.

- Можно использовать кортеж, который предоставляет простое решение для извлечения с несколькими возвращаемыми значениями.

Например **TryParse** методы возврата .NET `Boolean` значение, указывающее, успешно ли выполнена операция синтаксического анализа. Результат операции анализа возвращается в переменную, передаваемый по ссылке в метод. Как правило, вызов метода анализа, такие как <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> выглядит следующим образом:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Мы можем вернуться кортеж из операции анализа, если мы программу-оболочку вызова <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> в нашей методе. В следующем примере `NumericLibrary.ParseInteger` вызовы <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод и возвращает кортеж, именованный с двумя элементами. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Затем можно вызвать метод с помощью следующего кода:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic кортежи и кортежи в .NET Framework

Visual Basic кортеж представляет собой экземпляр одного из **System.ValueTuple** универсальных типов, которые впервые появились в .NET Framework 4.7. Платформа .NET Framework также включает набор универсального **System.Tuple** классы. Эти классы тем не менее, отличаются от кортежей Visual Basic и **System.ValueTuple** универсальных типов в следующих случаях:

- Элементы **кортежа** классы являются свойства с именем `Item1`, `Item2`, и т. д. В Visual Basic кортежей и **ValueTuple** поля, типы элементов кортежа.

- Элементы нельзя назначить значимые имена **кортежа** экземпляра или **ValueTuple** экземпляра. Visual Basic позволяет присваивать имена, которые смысловое значение поля.

- Свойства **кортежа** экземпляра доступны только для чтения; кортежи являются неизменяемыми. В Visual Basic кортежей и **ValueTuple** типы, поля кортежа, чтения и записи; кортежи может изменяться.

- Универсальный **кортежа** типы являются ссылочными типами. Используя эти **кортежа** типы означает выделение объектов. В критических путях это может заметно влиять на производительность приложения. Visual Basic кортежей и **ValueTuple** типы являются типами значений.

Методы расширения в <xref:System.TupleExtensions> класс облегчить преобразование между кортежи Visual Basic и .NET **кортежа** объектов. **ToTuple** метод преобразует кортеж Visual Basic .NET **кортежа** объекта и **ToValueTuple** метод преобразует .NET **кортежа** Объект кортежа Visual Basic.

Следующий пример создает кортеж, преобразует его в .NET **кортежа** объекта и преобразует его обратно кортеж Visual Basic. Затем в примере сравнивается этот кортеж исходной версией, чтобы убедиться, что они равны.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>См. также

[Справочник по языку Visual Basic](index.md)  
