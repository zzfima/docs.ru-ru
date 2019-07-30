---
title: Индексированные свойства
description: Сведения об индексированных свойствах F#в, которые позволяют обращаться к упорядоченным данным по подобному массиву.
ms.date: 10/17/2018
ms.openlocfilehash: 379417e31b8e178d8c939e5b23dc144bfb17e562
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627553"
---
# <a name="indexed-properties"></a>Индексированные свойства

При определении класса, который является абстрактным по отношению к упорядоченным данным, иногда может быть полезно предоставить индексированный доступ к этим данным без предоставления базовой реализации. Это делается с `Item` элементом.

## <a name="syntax"></a>Синтаксис

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Примечания

Формы предыдущего синтаксиса показывают, как определить индексированные свойства, которые содержат как, так `get` `set` и метод, имеют `get` только метод или имеют `set` только метод. Можно также сочетать синтаксис, показанный только для Get, и синтаксис, показанный только для Set, и создать свойство, которое имеет и Get, и Set. Эта последняя форма позволяет размещать в методах get и Set разные модификаторы и атрибуты доступа.

Используя имя `Item`, компилятор рассматривает свойство как индексированное свойство по умолчанию. *Индексированное свойство по умолчанию* — это свойство, доступ к которому можно получить с помощью синтаксиса, подобного массиву, в экземпляре объекта. Например, если `o` является объектом типа, определяющего это свойство, используется синтаксис `o.[index]` для доступа к свойству.

Синтаксис для доступа к индексированному свойству, не являющемуся по умолчанию, заключается в предоставлении имени свойства и индекса в круглых скобках, как и обычный элемент. Например, если свойство для `o` вызывается `Ordinal`, вы пишете `o.Ordinal(index)` его для доступа.

Независимо от используемой формы следует всегда использовать каррированных вида метода Set для индексированного свойства. Дополнительные сведения о каррированных функциях см. в разделе [функции](../functions/index.md).

## <a name="example"></a>Пример

В следующем примере кода показано определение и использование индексированных свойств по умолчанию и не являющихся свойствами по умолчанию, имеющих методы get и Set.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Вывод

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Индексированные свойства с несколькими значениями индекса

Индексированные свойства могут иметь более одного значения индекса. В этом случае при использовании свойства значения разделяются запятыми. Метод Set в таком свойстве должен иметь два каррированных аргумента, первый из которых является кортежем, содержащим ключи, а второй — заданным значением.

В следующем коде показано использование индексированного свойства с несколькими значениями индекса.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
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
