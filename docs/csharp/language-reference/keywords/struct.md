---
title: struct. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 95c36cd039436dcddd3e2e2a3e1fae98ee885677
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924668"
---
# <a name="struct-c-reference"></a>struct (справочник по C#)

Тип `struct` представляет собой тип значения, который обычно используется для инкапсуляции небольших групп связанных переменных, например координат прямоугольника или характеристик элемента в инвентаризации. В следующем примере показано простое объявление структуры:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Примечания

Структуры также могут содержать [конструкторы](../../programming-guide/classes-and-structs/constructors.md), [константы](../../programming-guide/classes-and-structs/constants.md), [поля](../../programming-guide/classes-and-structs/fields.md), [методы](../../programming-guide/classes-and-structs/methods.md), [свойства](../../programming-guide/classes-and-structs/properties.md), [индексаторы](../../programming-guide/indexers/index.md), [операторы](../operators/index.md), [события](../../programming-guide/events/index.md) и [вложенные типы](../../programming-guide/classes-and-structs/nested-types.md), хотя, если требуется несколько таких членов, тип необходимо заменить классом.

Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).

Структуры могут реализовать интерфейс, но не могут наследоваться из другой структуры. По этой причине члены структуры не могут объявляться как `protected`.

Дополнительные сведения см. в разделе [Структуры](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Примеры

Примеры и дополнительные сведения см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Примеры см. в разделе [Использование структур](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Таблица значений по умолчанию](default-values-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Типы](types.md)
- [Типы значений](value-types.md)
- [class](class.md)
- [interface](interface.md)
- [Классы и структуры](../../programming-guide/classes-and-structs/index.md)
