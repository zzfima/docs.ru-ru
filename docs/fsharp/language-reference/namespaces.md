---
title: Пространства имен (F#)
description: 'Узнайте, как пространство имен F # позволяет организовать код в области связанной функциональности, позволяя присоединить имя группирования элементов программы.'
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="namespaces"></a>Пространства имен

С помощью пространства имен вы можете упорядочить код по областям соответствующей функциональности, подключив имя к группированию элементов программы.


## <a name="syntax"></a>Синтаксис

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>Примечания
Если вы хотите поместить код в пространстве имен, первого объявления в файле необходимо объявить пространство имен. Содержимое этого файла становится частью пространства имен.

Пространства имен не может содержать непосредственно значения и функции. Вместо этого значения и функции должны быть включены в модулях, а модули включены в пространствах имен. Пространства имен могут содержать типы модулей.

Пространства имен может быть объявлено явно с помощью ключевого слова пространства имен или неявно при объявлении модуля. Чтобы объявить пространство имен явно, используйте ключевое слово namespace, за которым следует имя пространства имен. Приведенный ниже показан файл кода, который объявляет пространство имен мини-приложения с типом и модуль, содержащийся в этом пространстве имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Если все содержимое файла является частью одного модуля, можно также объявить пространств имен неявно с помощью `module` ключевое слово и новое имя пространства имен в полное имя модуля. В следующем примере показано файл кода, который объявляет пространство имен `Widgets` и модуль `WidgetsModule`, содержащего функцию.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Следующий код эквивалентен приведенный выше код, но модуль является объявление локального модуля. В этом случае пространство имен должно отображаться на отдельной строке.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Если требуется более чем в одном модуле в том же файле, в один или несколько пространств имен, необходимо использовать локальное объявление модулей. При использовании локальных объявления модулей, полное имя пространства имен нельзя использовать в объявлениях модуля. Ниже приведен файл, содержащий объявление пространства имен и два локальных объявления модулей. В этом случае модули содержатся непосредственно в пространстве имен; Нет не неявно созданного модуля, который имеет то же имя, что и файл. Любой другой код в файле, такие как `do` привязки, является в пространстве имен, но не во внутренних модулях, поэтому вам необходимо для уточнения члена модуля `widgetFunction` , используя имя модуля.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

Выходные данные этого примера выглядит следующим образом.

```fsharp
Module1 10 20
Module2 5 6
```

Дополнительные сведения см. в разделе [модулей](modules.md).

## <a name="nested-namespaces"></a>Вложенные пространства имен
При создании вложенных пространств имен, необходимо определить его полностью. В противном случае создается новое пространство имен верхнего уровня. Отступ игнорируется в объявления пространств имен.

В следующем примере показан способ объявления вложенных пространств имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Пространства имен в файлы и сборки
Пространства имен может охватывать несколько файлов проекта или компиляции. Термин *фрагмент пространства имен* описываются части пространства имен, который включен в один файл. Пространства имен также могут охватывать несколько сборок. Например `System` пространство имен включает весь .NET Framework, которая охватывает несколько сборок и содержит много вложенных пространств имен.


## <a name="global-namespace"></a>Глобальное пространство имен
Используйте стандартные пространства имен `global` включаемые имена в пространство имен .NET верхнего уровня.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

Можно также использовать глобальный для ссылки на пространство имен верхнего уровня .NET, например, чтобы устранить конфликты имен с другими пространствами имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Рекурсивные пространства имен

F # 4.1 вводится понятие пространства имен, которая разрешает все автономные кода взаимно рекурсивные.  Это выполняется через `namespace rec`.  Использование `namespace rec` можно устранить некоторые усилия невозможности писать код взаимно ссылочной между типами и модулей.  Ниже приведен пример этого:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.  Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.  Это будет невозможно выразить в F #, если вы удалили `rec` ключевое слово из `MutualReferences` пространства имен.

Эта функция также доступна для верхнего уровня [модули](modules.md) в F # 4.1 или более поздней версии.

## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Модули](modules.md)

[F # RFC FS-1009 - разрешить взаимно ссылочные типы и модули через большего пространства в файлах](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
