---
title: Индексированные свойства (F#)
description: 'Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к данным упорядоченный.'
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749599"
---
# <a name="indexed-properties"></a>Индексированные свойства

*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные. Они бывают трех видов:

* `Item`
* `Ordinal`
* `Cardinal`

В F # член должен иметь имя одного из этих трех имен, чтобы предоставить доступ через массив. `IndexerName` используется для представления любой из трех вариантов ниже:

## <a name="syntax"></a>Синтаксис

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Примечания

Виды выше синтаксисе показано, как определять индексированные свойства, для которых имеются обе `get` и `set` метод, имеют `get` только метод или иметь `set` только метод. Можно также комбинировать синтаксис, показанный для get только и синтаксис, показанный для набора только и получения свойства с get и set. Эта последняя форма позволяет поместить различные модификаторы доступности и атрибуты на get и методы работы с наборами.

Когда *IndexerName* является `Item`, компилятор считает свойство по умолчанию индексированное свойство. Объект *индексированное свойство по умолчанию* — это свойство, можно получить доступ, используя синтаксис, подобный массиву в экземпляре объекта. Например если `obj` — это объект типа, который определяет данное свойство синтаксис `obj.[index]` используется для доступа к свойству.

Синтаксис для доступа к не по умолчанию индексированное свойство является предоставление имени свойства и индекс в круглые скобки. Например, если свойство является `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.

Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству. Сведения о каррированные функции, см. в разделе [функции](../functions/index.md).

## <a name="example"></a>Пример

В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, которые имеют get и методы работы с наборами.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Вывод

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Индексированные свойства с несколькими переменными индекса

Индексированные свойства могут иметь более одной переменной индекса. В этом случае переменные разделяются запятыми при использовании свойства. Метод set в такое свойство должен иметь два каррированных аргумента, первый из которых представляет собой кортеж, содержащий ключи, а второй — задаваемое значение.

Следующий код демонстрирует использование индексированного свойства с несколькими переменными индекса.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a>См. также

- [Члены](index.md)
