---
title: Пространства имен (F#)
description: Узнайте, как пространство имен F# позволяет упорядочить код по областям соответствующей функциональности, предоставляя возможность присоединить имя к группированию элементов программы.
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "44178263"
---
# <a name="namespaces"></a>Пространства имен

С помощью пространства имен вы можете упорядочить код по областям соответствующей функциональности, подключив имя к группированию элементов программы.

## <a name="syntax"></a>Синтаксис

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>Примечания

Если вы хотите поместить код в пространстве имен, первого объявления в файле необходимо объявить пространство имен. Содержимое этого файла становится частью пространства имен.

Пространства имен не может непосредственно содержат значения и функции. Вместо этого значения и функции должны быть включены в модули и модули, включаются в пространствах имен. Пространства имен может содержать типы, модули.

Пространства имен может быть объявлен явным образом с помощью ключевого слова пространства имен или неявно при объявлении модуля. Чтобы объявить пространство имен явно, используйте ключевое слово namespace, за которым следует имя пространства имен. Следующий пример показывает файл кода, объявляющий пространство имен мини-приложения с типом и модуль, включенный в этом пространстве имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Если все содержимое файла находятся в одном модуле, можно также объявить пространства имен неявно с помощью `module` ключевое слово и имя нового пространства имен в полное имя модуля. В примере показан файл кода, объявляющий пространство имен `Widgets` и модуль `WidgetsModule`, содержащего функцию.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Следующий код эквивалентен предыдущему коду, но модуль является объявление локального модуля. В этом случае пространство имен должно отображаться на отдельной строке.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Если требуется несколько модулей в тот же файл в один или несколько пространств имен, необходимо использовать объявления локального модуля. При использовании локального модуля объявления, в объявлениях модуля нельзя использовать имя пространства имен. Ниже приведен файл, содержащий объявление пространства имен и два объявления локального модуля. В этом случае модули содержатся непосредственно в пространстве имен; Нет не неявно созданного модуля, который имеет то же имя, что и файл. Любой другой код в файле, такие как `do` привязки, — в пространстве имен, но не в внутренних модулей, поэтому необходимо уточнить член модуля `widgetFunction` , используя имя модуля.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

Выходные данные этого примера выглядит следующим образом.

```fsharp
Module1 10 20
Module2 5 6
```

Дополнительные сведения см. в разделе [модули](modules.md).

## <a name="nested-namespaces"></a>Вложенные пространства имен

При создании вложенного пространства имен, необходимо полностью указать его. В противном случае можно создать новое пространство имен верхнего уровня. Отступ игнорируется в объявлениях пространств имен.

В следующем примере показан способ объявления вложенного пространства имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Пространства имен в файлы и сборки

Пространства имен может охватывать несколько файлов проекта или компиляции. Термин *фрагмент пространства имен* описывает часть пространства имен, которое включено в один файл. Пространства имен также могут охватывать несколько сборок. Например `System` пространство имен включает всей .NET Framework, которая охватывает несколько сборок и содержит много вложенных пространств имен.

## <a name="global-namespace"></a>Глобальное пространство имен

Используйте стандартные пространства имен `global` поместить имена в пространство имен верхнего уровня .NET.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

Можно также использовать глобальный для ссылки на пространство имен .NET верхнего уровня, например, чтобы устранить конфликты имен с другими пространствами имен.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Рекурсивные пространств имен

F# 4.1, вводится понятие пространств имен, которая допускает все автономной кода взаимно рекурсивные.  Это делается с помощью `namespace rec`.  Использование `namespace rec` могут помочь в решении некоторые трудности в не возможность написания кода в взаимно ссылочные типы и модули.  Ниже приведен пример этого:

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

Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.  Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.  Это не позволяет выражать в F#, если вы удалили `rec` ключевое слово from `MutualReferences` пространства имен.

Эта функция также доступна для верхнего уровня [модули](modules.md) в F# 4.1 или более поздней версии.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Модули](modules.md)
- [F# RFC FS-1009 - разрешить взаимно ссылочные типы и модули через большего пространства в файлах](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
