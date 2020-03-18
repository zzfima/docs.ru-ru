---
title: Справочник по C#. Ключевое слово protected
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713187"
---
# <a name="protected-c-reference"></a>protected (справочник по C#)

Ключевое слово `protected` является модификатором доступа к члену.

 > Эта страница содержит доступ `protected`. Ключевое слово `protected` также является частью модификаторов доступа [`protected internal`](protected-internal.md) и [`private protected`](private-protected.md).

Доступ к защищенному элементу может быть получен из соответствующего класса, а также экземплярами производных классов.

Сравнение модификатора `protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).

## <a name="example"></a>Пример

Доступ к защищенному элементу базового класса может быть получен в производном классе, только если доступ осуществляется через тип производного класса. Для примера рассмотрим следующий сегмент кода:

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

Оператор `a.x = 10` вызывает ошибку, поскольку выполняется в статическом методе Main, а не в экземпляре класса Б.

Элементы структуры защитить нельзя, поскольку структура не может наследоваться.

## <a name="example"></a>Пример

В этом примере класс `DerivedPoint` является производным от класса `Point`. В связи с этим доступ к защищенным элементам базового класса можно получить напрямую из производного класса.

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

Если изменить уровни доступа `x` и `y` на [private](private.md), компилятор выдаст сообщения об ошибках:

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы доступа](access-modifiers.md)
- [Уровни доступности](accessibility-levels.md)
- [Модификаторы](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
