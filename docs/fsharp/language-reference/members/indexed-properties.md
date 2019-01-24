---
title: Индексированные свойства
description: Дополнительные сведения о индексированных свойств в F#, разрешающее для доступ через массив к упорядоченных данных.
ms.date: 10/17/2018
ms.openlocfilehash: a092da753acacf80807d145051a719df2d3e1520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550972"
---
# <a name="indexed-properties"></a>Индексированные свойства

При определении класс, который абстрагирует упорядоченный данными, иногда бывает полезно предоставить индексированный доступ к этим данным без предоставления базовой реализации. Это делается с помощью `Index` член.

## <a name="syntax"></a>Синтаксис

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Примечания

Виды выше синтаксисе показано, как определять индексированные свойства, для которых имеются обе `get` и `set` метод, имеют `get` только метод или иметь `set` только метод. Можно также комбинировать синтаксис, показанный для get только и синтаксис, показанный для набора только и получения свойства с get и set. Эта последняя форма позволяет поместить различные модификаторы доступности и атрибуты на get и методы работы с наборами.

С помощью имени `Item`, компилятор считает свойство по умолчанию индексированное свойство. Объект *индексированное свойство по умолчанию* — это свойство, можно получить доступ, используя синтаксис, подобный массиву в экземпляре объекта. Например если `o` — это объект типа, который определяет данное свойство синтаксис `o.[index]` используется для доступа к свойству.

Синтаксис для доступа к не по умолчанию индексированное свойство является предоставление имени свойства и индекс в круглые скобки, так же, как обычный член. Например если свойство `o` называется `Ordinal`, написании `o.Ordinal(index)` для доступа к нему.

Независимо от того, какая форма используется следует всегда использовать Каррированная форма для метода set по индексированному свойству. Сведения о каррированные функции, см. в разделе [функции](../functions/index.md).

## <a name="example"></a>Пример

В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, которые имеют get и методы работы с наборами.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Вывод

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Индексированные свойства с несколькими значениями индекса

Индексированные свойства могут иметь более одного значения индекса. В этом случае значения разделяются запятыми, при использовании свойства. Метод set в такое свойство должен иметь два каррированных аргумента, первый из которых представляет собой кортеж, содержащий ключи, а второй — задаваемое значение.

Следующий код демонстрирует использование индексированного свойства с несколькими значениями индекса.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix basedon a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a>См. также

- [Члены](index.md)
