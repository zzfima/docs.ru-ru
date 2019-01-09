---
title: Справочник по C#. Ключевое слово readonly
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: dfbeb5ff94f39e8d8df03feea9ff55db748d2182
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058585"
---
# <a name="readonly-c-reference"></a>readonly (Справочник по C#)

Ключевое слово `readonly` — это модификатор, который может использоваться в трех контекстах:

- В [объявлении поля](#readonly-field-example) `readonly` указывает на то, что присвоение значения полю может происходить только при объявлении или в конструкторе этого класса.
- В [определении `readonly struct`](#readonly-struct-example) `readonly` указывает на то, что `struct` является неизменяемым.
- В [возврате метода](#ref-readonly-return-example) `ref readonly` модификатор `readonly` указывает, что метод возвращает ссылку, и записи для этой ссылки не допускаются.

Последние два контекста были добавлены в C# 7.2.

## <a name="readonly-field-example"></a>Пример поля только для чтения

В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

Можно присвоить значение полю `readonly` только в следующих контекстах:

- Когда переменная инициализируется в объявлении, например:

```csharp
public readonly int y = 5;
```

- В конструкторе экземпляра класса, содержащего объявление поля экземпляра.
- В статическом конструкторе класса, содержащего объявление статического поля.

Эти контексты конструктора являются единственными, в которых можно передавать поле `readonly` в качестве параметра [out](out-parameter-modifier.md) или [ref](ref.md).

> [!NOTE]
> Ключевое слово `readonly` отличается от ключевого слова [const](const.md). Поле `const` может быть инициализировано только при объявлении поля. Поле `readonly` может быть назначено несколько раз в объявлении поля и в любом конструкторе. Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора. К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

В предыдущем примере при использовании такого оператора:

`p2.y = 66;        // Error`

будет отображено сообщение об ошибке компилятора:

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a>Пример структуры только для чтения

Модификатор `readonly` в определении `struct` объявляет, что структура является **неизменяемой**. Каждое поле экземпляра `struct` должно быть помечено `readonly`, как показано в следующем примере:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

В предыдущем примере используются [автоматические свойства только для чтения](../../properties.md#read-only) для объявления хранилища. Это указывает компилятору на необходимость создания резервных полей `readonly` для этих свойств. Можно также объявить поля `readonly` напрямую:

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

Добавление поля без отметки `readonly` вызывает ошибку компилятора `CS8340` с информацией о том, что поля экземпляров в структурах только для чтения должны быть доступными только для чтения.

## <a name="ref-readonly-return-example"></a>Пример возвращаемой ссылки только для чтения

Модификатор `readonly` в `ref return` указывает, что возвращаемую ссылку нельзя изменить. Следующий пример возвращает ссылку на источник. Он использует модификатор `readonly`, чтобы указать, что вызывающие объекты не могут изменять источник:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Необязательно должен возвращаться тип `readonly struct`. Любой тип, возвращаемый `ref`, может возвращаться `ref readonly`

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы](modifiers.md)
- [const](const.md)
- [Поля](../../programming-guide/classes-and-structs/fields.md)
