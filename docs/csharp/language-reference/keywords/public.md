---
title: Ключевое слово public (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518190"
---
# <a name="public-c-reference"></a>public (справочник по C#)

Ключевое слово `public` является модификатором доступа для типов и членов типов. Общий доступ является уровнем доступа с максимальными правами. Ограничений доступа к общим членам не существует, как показано в следующем примере:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Дополнительные сведения см. в разделах [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](accessibility-levels.md).

## <a name="example"></a>Пример

В следующем примере объявляются два класса: `PointTest` и `MainClass`. Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

Если уровень доступа `public` изменить на [private](private.md) или [protected](protected.md), будет выводится следующее сообщение об ошибке:

"PointTest.y" недоступен из-за его уровня защиты.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы доступа](access-modifiers.md)
- [Уровни доступности](accessibility-levels.md)
- [Модификаторы](modifiers.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)