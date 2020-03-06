---
title: Справочник по C#. Ключевое слово class
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673099"
---
# <a name="class-c-reference"></a>класс (Справочник по C#)

Классы объявляются с помощью ключевого слова `class`, как показано в следующем примере:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a>Примечания

В C# допускается только одиночное наследование. Другими словами, класс может наследовать реализацию только от одного базового класса. Однако класс может реализовывать несколько интерфейсов. В таблице ниже приведены примеры наследования класса и реализации интерфейса.

|Наследование|Пример|
|-----------------|-------------|
|Отсутствуют|`class ClassA { }`|
|Single|`class DerivedClass : BaseClass { }`|
|Отсутствует, реализует два интерфейса|`class ImplClass : IFace1, IFace2 { }`|
|Одиночное, реализует один интерфейс|`class ImplDerivedClass : BaseClass, IFace1 { }`|

Классы, объявленные непосредственно в пространстве имен и не вложенные в другие классы, могут быть [открытыми](./public.md) или [внутренними](./internal.md). По умолчанию классы являются `internal`.

Члены класса, включая вложенные классы, могут объявляться с типом доступа [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) или [private protected](private-protected.md). По умолчанию члены имеют тип доступа `private`.

Дополнительные сведения см. в статье [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).

Можно объявить универсальные классы, имеющие параметры типа. Дополнительные сведения см. в разделе [Универсальные классы](../../programming-guide/generics/generic-classes.md).

Класс может содержать объявления следующих членов:

- [Конструкторы](../../programming-guide/classes-and-structs/constructors.md)

- [Константы](../../programming-guide/classes-and-structs/constants.md)

- [Поля](../../programming-guide/classes-and-structs/fields.md)

- [Методы завершения](../../programming-guide/classes-and-structs/destructors.md)

- [Методы](../../programming-guide/classes-and-structs/methods.md)

- [Свойства](../../programming-guide/classes-and-structs/properties.md)

- [Индексаторы](../../programming-guide/indexers/index.md)

- [Инструкции](../operators/index.md)

- [События](../../programming-guide/events/index.md)

- [Делегаты](../../programming-guide/delegates/index.md)

- [Классы](../../programming-guide/classes-and-structs/classes.md)

- [Интерфейсы](../../programming-guide/interfaces/index.md)

- [Типы структур](../builtin-types/struct.md)

- [Типы перечислений](../builtin-types/enum.md)

## <a name="example"></a>Пример

В приведенном ниже примере показано объявление полей, конструкторов и методов класса. В нем также демонстрируется создание экземпляра объекта и печать данных экземпляра. В этом примере объявляются два класса. Первый класс, `Child`, содержит два частных поля (`name` и `age`), два общих конструктора и один общий метод. Второй класс, `StringTest`, используется для хранения `Main`.

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a>Комментарии

Обратите внимание, что в предыдущем примере доступ к частным полям (`name` и `age`) возможен только с помощью общих методов класса `Child`. Например, имя ребенка нельзя напечатать из метода `Main` с помощью следующего оператора:

```csharp
Console.Write(child1.name);   // Error
```

Получить доступ к закрытым членам класса `Child` из метода `Main` можно было бы лишь в том случае, если бы `Main` был членом класса.

Типы, объявленные в классе без модификатора доступа, по умолчанию являются `private`, поэтому члены данных в этом примере останутся `private`, если ключевые слова будут удалены.

Наконец, обратите внимание, что для объекта, созданного с помощью конструктора без параметров (`child3`), поле `age` по умолчанию инициализировано с нулевым значением.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [Ссылочные типы](./reference-types.md)
