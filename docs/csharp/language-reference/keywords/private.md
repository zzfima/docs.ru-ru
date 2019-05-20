---
title: Справочник по C#. Ключевое слово private
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
ms.openlocfilehash: 67b2621d382651abc27cee2eadad91a6253895c1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633327"
---
# <a name="private-c-reference"></a>private (Справочник по C#)

Ключевое слово `private` является модификатором доступа к члену.

> Эта страница содержит доступ `private`. Ключевое слово `private` также является частью модификатора доступа [`private protected`](./private-protected.md).

Закрытый доступ является уровнем доступа с минимальными правами. Доступ к закрытым членам можно получить только внутри тела класса или структуры, в которой они объявлены, как показано в следующем примере:

```csharp
class Employee
{
    private int i;
    double d;   // private access by default
}
```

Вложенные типы в том же теле могут также обращаться к таким закрытым членам.

Ошибка времени компиляции возникнет в том случае, если создать ссылку на закрытый член за пределами класса или структуры, в которой он объявлен.

Сравнение модификатора `private` с другими модификаторами доступа см. в разделах [Уровни доступности](accessibility-levels.md) и [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="example"></a>Пример

В этом примере класс `Employee` содержит два закрытых элемента данных — `name` и `salary`. Как к закрытым членам, к ним нельзя получить доступ, кроме как через методы членов. Для получения управляемого доступа к закрытым членам можно использовать открытые методы `GetName` и `Salary`. Доступ к члену `name` можно поучить через открытый метод, а к члену `salary` — через открытое свойство только для чтения. (Дополнительные сведения см. в разделе [Свойства](../../programming-guide/classes-and-structs/properties.md).)

[!code-csharp[csrefKeywordsModifiers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#10)]

## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы доступа](access-modifiers.md)
- [Уровни доступности](accessibility-levels.md)
- [Модификаторы](modifiers.md)
- [public](public.md)
- [protected](protected.md)
- [internal](internal.md)
