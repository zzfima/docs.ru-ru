---
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343955"
---
# <a name="object-data-type"></a>Object Data Type

Содержит адреса, которые ссылаются на объекты. В переменную `Object` можно назначить любой ссылочный тип (строка, массив, класс или интерфейс). `Object`ая переменная может также ссылаться на данные любого типа значения (numeric, `Boolean`, `Char`, `Date`, структуры или перечисления).

## <a name="remarks"></a>Заметки

Тип данных `Object` может указывать на данные любого типа данных, включая любой экземпляр объекта, распознаваемый приложением. Используйте `Object`, если во время компиляции неизвестно, на какой тип данных может указывать переменная.

Значение `Object` по умолчанию — `Nothing` (пустая ссылка).

## <a name="data-types"></a>Типы данных

Переменной `Object` можно присвоить переменную, константу или выражение любого типа данных. Чтобы определить тип данных, на который в настоящее время ссылается переменная `Object`, можно использовать метод <xref:System.Type.GetTypeCode%2A> класса <xref:System.Type?displayProperty=nameWithType>. Это показано в следующем примере.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Тип данных `Object` является ссылочным типом. Однако Visual Basic обрабатывает переменную `Object` как тип значения, если она ссылается на данные типа значения.

## <a name="storage"></a>Хранилище

Любой тип данных, на который он ссылается, `Object`ая переменная не содержит само значение данных, а указатель на это значение. Он всегда использует четыре байта в памяти компьютера, но не включает хранилище для данных, представляющих значение переменной. Из-за кода, использующего указатель для нахождение данных, `Object` переменные, удерживающие типы значений, немного медленнее, чем явно типизированные переменные.

## <a name="programming-tips"></a>Советы по программированию

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что типы указателей в других средах несовместимы с типом `Object` Visual Basic.

- **Производительность.** Переменная, объявляемая с типом `Object`, достаточно гибка, чтобы содержать ссылку на любой объект. Однако при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения). Чтобы принудительно выполнить *раннее связывание* (во время компиляции) и повысить производительность, объявите переменную с конкретным именем класса или приведите ее к конкретному типу данных.

  При объявлении объектной переменной попробуйте использовать конкретный тип класса, например <xref:System.OperatingSystem>, вместо обобщенного типа `Object`. Следует также использовать наиболее конкретный доступный класс, например <xref:System.Windows.Forms.TextBox> вместо <xref:System.Windows.Forms.Control>, чтобы получить доступ к его свойствам и методам. Для поиска доступных имен классов обычно можно использовать список **классы** в **обозревателе объектов** .

- **Расширяющие.** Все типы данных и все ссылочные типы расширяются до `Object`ного типа данных. Это означает, что можно преобразовать любой тип в `Object` без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.

  Однако при преобразовании типов значений и `Object`Visual Basic выполняет операции, которые называются *упаковкой-преобразованием* *и*распаковкой, что делает выполнение более медленным.

- **Символы типа.** `Object` не имеет символа типа литерала или символа типа идентификатора.

- **Тип платформы.** Соответствующий тип в .NET Framework является классом <xref:System.Object?displayProperty=nameWithType>.

## <a name="example"></a>Пример

В следующем примере показана переменная `Object`, указывающая на экземпляр объекта.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Практическое руководство. Определение наличия связи между двумя объектами](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
