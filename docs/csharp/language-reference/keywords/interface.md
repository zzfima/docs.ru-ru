---
title: interface. Справочник по C#
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625856"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface"::: (справочник по C#)

Интерфейс определяет контракт. Любой [`class`](class.md) или [`struct`](../builtin-types/struct.md), реализующий этот контракт, должен предоставлять реализацию для членов, определенных в интерфейсе. Начиная с C# 8.0, интерфейс может определять реализацию по умолчанию для членов. Он также может определять члены [`static`](static.md), чтобы обеспечить единую реализацию для общих функциональных возможностей.

В следующем примере класс `ImplementationClass` должен реализовать метод с именем `SampleMethod`, не имеющий параметров и возвращающий значение `void`.

Дополнительные сведения и примеры см. в разделе [Интерфейсы](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Интерфейс может быть членом пространства имен или класса. Объявление интерфейса может содержать объявления (сигнатуры без реализации) следующих членов.

- [Методы](../../programming-guide/classes-and-structs/methods.md)
- [Свойства](../../programming-guide/classes-and-structs/using-properties.md)
- [Индексаторы](../../programming-guide/indexers/using-indexers.md)
- [События](event.md)

Эти предыдущие объявления членов обычно не содержат тело. Начиная с C# 8.0, член интерфейса может объявлять тело. Этот называется *реализацией по умолчанию*. Члены с телом позволяют интерфейсу предоставлять реализацию по умолчанию для классов и структур, которые не предоставляют реализацию с переопределением. Кроме того, начиная с C# 8.0, интерфейс может включать следующее.

- [Константы](const.md)
- [Операторы](../operators/operator-overloading.md)
- [Статический конструктор](../../programming-guide/classes-and-structs/constructors.md#static-constructors)
- [Вложенные типы](../../programming-guide/classes-and-structs/nested-types.md)
- [Статические поля, методы, свойства, индексаторы и события](static.md)
- Объявления членов с использованием синтаксиса явной реализации интерфейса.
- Явные модификаторы доступа (доступ по умолчанию — [`public`](access-modifiers.md)).

Интерфейсы не могут содержать состояние экземпляра. Хотя статические поля теперь разрешены, поля экземпляров в интерфейсах запрещены. [Автосвойства экземпляра](../../programming-guide/classes-and-structs/auto-implemented-properties.md) не поддерживаются в интерфейсах, так как они неявно объявляют скрытое поле. Это правило оказывает незначительное воздействие на объявления свойств. В объявлении интерфейса следующий код не объявляет автоматически реализуемое свойство, как в `class` или `struct`. Вместо этого он объявляет свойство, которое не имеет реализации по умолчанию, но должно быть реализовано в любом типе, реализующем интерфейс.

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

Интерфейс может наследовать от одного или нескольких базовых интерфейсов. Когда интерфейс [переопределяет метод](override.md), реализованный в базовом интерфейсе, он должен использовать синтаксис [явной реализации интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).

Если список базовых типов содержит базовый класс и интерфейсы, базовый класс должен стоять первым в списке.

Класс, реализующий интерфейс, может явно реализовывать члены этого интерфейса. При явной реализации члена к нему можно получить доступ только через экземпляр интерфейса, но не через экземпляр класса. Кроме того, обращение к членам интерфейса по умолчанию можно осуществлять только через экземпляр интерфейса.

Дополнительные сведения о явной реализации интерфейса см. в статье [Явная реализация интерфейса](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Пример

В следующем примере показана реализация интерфейса. В этом примере интерфейс содержит объявление свойства, а класс содержит реализацию. Любой экземпляр класса, который реализует `IPoint`, имеет целочисленные свойства `x` и `y`.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Интерфейсы](~/_csharplang/spec/interfaces.md) статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md), а также в спецификации функций для [элементов интерфейса по умолчанию — C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md).

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Ссылочные типы](reference-types.md)
- [Интерфейсы](../../programming-guide/interfaces/index.md)
- [Использование свойств](../../programming-guide/classes-and-structs/using-properties.md)
- [Использование индексаторов](../../programming-guide/indexers/using-indexers.md)
- [Интерфейсы](../../programming-guide/interfaces/index.md)
