---
title: "Индексированные свойства (F#)"
description: "Дополнительные сведения о F # индексированные свойства, которые являются свойства, предоставляющие доступ через массив к упорядоченным данным."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f1266b8b-e2e3-4f49-9332-65c6d34dc0f3
ms.openlocfilehash: 78a09a70621e82f073346471e68ec826359641d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="indexed-properties"></a>Индексированные свойства

*Индексированные свойства* свойства, предоставляющие доступ через массив к упорядочиваются данные.


## <a name="syntax"></a>Синтаксис

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Примечания
Три вида предыдущем синтаксисе показывают, как определять индексированные свойства, имеющие и `get` и `set` метод, имеют `get` только метод или иметь `set` только метод. Можно также комбинировать показано только получение и синтаксис, показанный для набора только синтаксис и создать свойство, имеющее get и set. Эта последняя форма позволяет размещать различные модификаторы доступности и атрибуты на get методов и set.

Когда *PropertyName* — `Item`, компилятор рассматривает свойство как индексированное свойство по умолчанию. Объект *индексированное свойство по умолчанию* — это свойство, к которой можно обращаться, используя синтаксис, подобный массиву на экземпляр объекта. Например если `obj` — это объект типа, который определяет это свойство синтаксис `obj.[index]` используется для доступа к свойству.

Синтаксис для доступа к не по умолчанию индексированное свойство — для предоставления имени свойства и индекса в круглых скобках. Например, если свойство `Ordinal`, написании `obj.Ordinal(index)` для доступа к нему.

Независимо от того, какая форма используется, следует всегда использовать каррированные для `set` метод по индексированному свойству. Сведения о каррированные функции см. в разделе [функции](../functions/index.md).

## <a name="example"></a>Пример

В следующем примере кода показано определение и использование по умолчанию и не по умолчанию индексированные свойства, задать методы get и.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Вывод

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Индексированные свойства с несколькими переменными индекса
Индексированные свойства могут иметь более одной переменной индекса. В этом случае переменные разделяются запятыми при использовании свойства. Метод set в таком свойстве должен иметь два переданными аргументами, первым из которых — кортеж, содержащий ключи, а второй — задаваемое значение.

В следующем коде показано использование индексированного свойства с несколькими переменными индекса.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a>См. также
[Члены](index.md)
