---
title: interface. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 19ca4b8a490dc85de0d0e2be6d3ca8fa7982fc14
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713437"
---
# <a name="interface-c-reference"></a>interface (Справочник по C#)

Интерфейс содержит только сигнатуры [методов](../../programming-guide/classes-and-structs/methods.md), [свойств](../../programming-guide/classes-and-structs/properties.md), [событий](../../programming-guide/events/index.md) или [индексаторов](../../programming-guide/indexers/index.md). Класс или структура, реализующие интерфейс, должны реализовать члены интерфейса, заданные в определении интерфейса. В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.

Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Интерфейс может быть членом пространства имен или класса и содержать сигнатуры следующих членов:

- [Методы](../../programming-guide/classes-and-structs/methods.md)

- [Свойства](../../programming-guide/classes-and-structs/using-properties.md)

- [Индексаторы](../../programming-guide/indexers/using-indexers.md)

- [События](event.md)

Интерфейс может наследовать от одного или нескольких базовых интерфейсов.

Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.

Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса. При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса.

Дополнительные сведения и примеры кода с явной реализацией интерфейса см. в разделе [Явная реализация интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Пример

В следующем примере показана реализация интерфейса. В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию. Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Ссылочные типы](reference-types.md)
- [Интерфейсы](../../programming-guide/interfaces/index.md)
- [Использование свойств](../../programming-guide/classes-and-structs/using-properties.md)
- [Использование индексаторов](../../programming-guide/indexers/using-indexers.md)
- [class](class.md)
- [struct](struct.md)
- [Интерфейсы](../../programming-guide/interfaces/index.md)
