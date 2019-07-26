---
title: Тип данных Object (Visual Basic)
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
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513047"
---
# <a name="object-data-type"></a>Object Data Type

Содержит адреса, которые ссылаются на объекты. В `Object` переменную можно назначить любой ссылочный тип (строка, массив, класс или интерфейс). Переменная также может ссылаться на данные любого типа значения ( `Char`числовой, `Boolean` `Date`,,, структура или перечисление). `Object`

## <a name="remarks"></a>Примечания

Тип `Object` данных может указывать на данные любого типа данных, включая любой экземпляр объекта, распознаваемый приложением. Используйте `Object` , если во время компиляции неизвестно, на какой тип данных может указывать переменная.

Значение `Object` по умолчанию — `Nothing` (пустая ссылка).

## <a name="data-types"></a>Типы данных

Переменной можно присвоить переменную, константу или выражение любого типа `Object` данных. Чтобы определить тип `Object` данных, на который в настоящее время ссылается переменная, можно <xref:System.Type.GetTypeCode%2A> использовать метод <xref:System.Type?displayProperty=nameWithType> класса. Это показано в следующем примере.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Тип `Object` данных является ссылочным типом. Однако Visual Basic обрабатывает `Object` переменную как тип значения, если она ссылается на данные типа значения.

## <a name="storage"></a>Хранилище

Любой тип данных, на который он ссылается `Object` , переменная не содержит само значение данных, а указатель на это значение. Он всегда использует четыре байта в памяти компьютера, но не включает хранилище для данных, представляющих значение переменной. Из-за кода, использующего указатель для нахождение данных, `Object` переменные, содержащие типы значений, немного медленнее, чем явно типизированные переменные.

## <a name="programming-tips"></a>Советы по программированию

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что типы указателей в других средах несовместимы с `Object` типом Visual Basic.

- **Производительность.** Переменная, объявляемая с `Object` типом, достаточно гибка, чтобы содержать ссылку на любой объект. Однако при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* (во время выполнения). Чтобы принудительно выполнить *раннее связывание* (во время компиляции) и повысить производительность, объявите переменную с конкретным именем класса или приведите ее к конкретному типу данных.

  При объявлении объектной переменной попробуйте использовать конкретный тип класса, например <xref:System.OperatingSystem>, вместо `Object` обобщенного типа. Также следует использовать наиболее конкретный класс, например <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control>, вместо, чтобы получить доступ к его свойствам и методам. Для поиска доступных имен классов обычно можно использовать список **классы** в **обозревателе объектов** .

- **Расширяющие.** Все типы данных и все ссылочные типы расширяются `Object` до типа данных. Это означает, что можно преобразовать любой тип `Object` в без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.

  Однако при преобразовании между типами значений и `Object`Visual Basic выполняет операции, называемые *упаковкой* и распаковкой, что делает выполнение более медленным.

- **Символы типа.** `Object`не имеет символа типа литерала или символа типа идентификатора.

- **Тип платформы.** Соответствующий тип в .NET Framework — это <xref:System.Object?displayProperty=nameWithType> класс.

## <a name="example"></a>Пример

В следующем примере показана `Object` переменная, указывающая на экземпляр объекта.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>См. также

- <xref:System.Object>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Практическое руководство. Определить, связаны ли два объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Практическое руководство. Определить, идентичны ли два объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
