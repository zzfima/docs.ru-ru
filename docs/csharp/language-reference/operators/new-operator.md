---
title: Справочник по C#. Оператор new
ms.date: 06/25/2019
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 84131bc503a106961419a27fc4e3e0f2d82306a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846237"
---
# <a name="new-operator-c-reference"></a>Оператор new (справочник по C#)

Оператор `new` создает экземпляр типа.

Ключевое слово `new` можно также использовать как [модификатор объявления члена](../keywords/new-modifier.md) или [ограничение универсального типа](../keywords/new-constraint.md).

## <a name="constructor-invocation"></a>Вызов конструктора

Для создания экземпляра типа обычно вызывается один из [конструкторов](../../programming-guide/classes-and-structs/constructors.md) этого типа с помощью оператора `new`:

[!code-csharp-interactive[invoke constructor](snippets/NewOperator.cs#Constructor)]

Для создания экземпляра объекта и его инициализации в одном операторе можно использовать [инициализатор объекта или элементов](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) с оператором `new`, как в следующем примере:

[!code-csharp-interactive[constructor with initializer](snippets/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a>создание массива

С помощью оператора `new` можно также создать экземпляр массива, как показано в следующем примере:

[!code-csharp-interactive[create array](snippets/NewOperator.cs#Array)]

Чтобы создать экземпляр массива и заполнить его элементами в одном операторе, используйте синтаксис инициализации массива. В следующем примере показаны различные способы сделать это:

[!code-csharp-interactive[initialize array](snippets/NewOperator.cs#ArrayInitialization)]

Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).

## <a name="instantiation-of-anonymous-types"></a>Создание экземпляров анонимных типов

Чтобы создать экземпляр [анонимного типа](../../programming-guide/classes-and-structs/anonymous-types.md), используйте оператор `new` и синтаксис инициализации объекта:

[!code-csharp-interactive[anonymous type](snippets/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>Уничтожение экземпляров типа

Уничтожать ранее созданные экземпляры типа необязательно. Экземпляры как ссылочных типов, так и типов значений уничтожаются автоматически. Экземпляры типов значений уничтожаются, как только уничтожается содержащий их контекст. Экземпляры ссылочных типов уничтожаются [сборщиком мусора](../../../standard/garbage-collection/index.md) в неуказанное время после удаления последней ссылки на них.

Для экземпляров типа, которые содержат неуправляемые ресурсы, например дескриптор файла, рекомендуется использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы. Дополнительные сведения см. в справке по API <xref:System.IDisposable?displayProperty=nameWithType> и статье об [операторе using](../keywords/using-statement.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательский тип не может перегружать оператор `new`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор new](~/_csharplang/spec/expressions.md#the-new-operator)[спецификация языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Инициализаторы объектов и коллекций](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
