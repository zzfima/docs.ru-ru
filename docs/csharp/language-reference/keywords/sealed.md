---
title: Модификатор sealed. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: 84f838645bed6facc8b59ebf596d16373a9c6f86
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422374"
---
# <a name="sealed-c-reference"></a>sealed (Справочник по C#)

При применении к классу модификатор `sealed` запрещает другим классам наследовать от этого класса. В следующем примере класс `B` наследует от класса `A`, но никакие классы не могут наследовать от класса `B`.

```csharp
class A {}
sealed class B : A {}
```

Модификатор `sealed` можно использовать для метода или свойства, которое переопределяет виртуальный метод или свойство в базовом классе. Это позволяет классам наследовать от вашего класса, запрещая им при этом переопределять определенные виртуальные методы или свойства.

## <a name="example"></a>Пример

В следующем примере класс `Z` наследует от класса `Y`, но `Z` не может переопределить виртуальную функцию `F`, которая объявлена в классе `X` и запечатана в классе `Y`.

[!code-csharp[csrefKeywordsModifiers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#16)]

Чтобы предотвратить переопределение производных классов при определении новых методов или свойств, не назначайте их в качестве виртуальных ([virtual](virtual.md)).

Нельзя использовать модификатор [abstract](abstract.md) с запечатанным классом, поскольку абстрактный класс должен наследоваться классом, реализующим абстрактные методы или свойства.

При применении к методу или свойству модификатор `sealed` всегда следует использовать с [override](override.md).

Поскольку структуры неявно запечатаны, их нельзя наследовать.

Дополнительные сведения см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).

Дополнительные примеры см. в разделе [Абстрактные и запечатанные классы и члены классов](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsModifiers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#17)]

Чтобы наследовать от запечатанного класса, можно применить следующую инструкцию в приведенном выше примере:

`class MyDerivedC: SealedClass {}   // Error`

В результате выдается сообщение об ошибке:

`'MyDerivedC': cannot derive from sealed type 'SealedClass'`

## <a name="remarks"></a>Примечания

Чтобы определить, нужно ли запечатывать класс, метод или свойство, имейте в виду следующее:

- потенциальные преимущества, которые производные классы могут получить от возможности настраивать ваш класс;

- вероятность того, что производные классы могут корректировать ваши классы, препятствуя их нормальной работе.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [Абстрактные и запечатанные классы и члены классов](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Модификаторы](index.md)
- [override](override.md)
- [virtual](virtual.md)
