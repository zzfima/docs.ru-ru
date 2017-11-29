---
title: "Модули (F#)"
description: "Узнайте, как модуль F # — это группирование кода F #, например значений, типов и значений функций, в программе F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 46de2d18-da51-40fa-a262-92edecada79d
ms.openlocfilehash: 89401c1f889be6c5585a302e3a7ac62478573b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="modules"></a>Модули

В контексте языка F # *модуль* — это группирование кода F #, например значений, типов и значений функций, в программе F #. Код группирования в модулях объединяет связанный код и помогает избежать конфликтов имен в программе.

## <a name="syntax"></a>Синтаксис

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>Примечания
Модуль F # — это группирование конструкций кода F #, например типов, значений, значений функций и кода в `do` привязки. Он реализован в виде общего класса среды выполнения (CLR) языка, содержит только статические члены. Существует два типа объявлений модулей, в зависимости от того, включен ли в модуль файл целиком: объявление модуля верхнего уровня и объявление локального модуля. Объявление модуля верхнего уровня содержит весь файл в модуле. Объявление модуля верхнего уровня может появиться только как первого объявления в файле.

В синтаксисе объявления модуля верхнего уровня, необязательные *полное пространство имен* последовательность вложенных имен пространств имен, содержащую модуль. Полное имя пространства имен не требуется быть ранее объявлено.

Необходимо отступы при объявлении модуля верхнего уровня. Вы имеете расстановка отступов во всем объявлениям в локальные модули. В объявлении локального модуля только объявления, отображаются с отступом внутри объявления являются частью этого модуля.

Если файл с кодом не начинается с объявления модуля верхнего уровня или объявление пространства имен, все содержимое файла, включая все локальные модули, становится частью неявно созданного модуля верхнего уровня, который имеет то же имя, что и файл без расширения, с первой буквой, переведенную в верхний регистр. Например рассмотрим следующий файл.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Этот файл будет скомпилирован, как если бы он был оформлен таким образом:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Если в файле имеется несколько модулей, необходимо использовать объявление локального модуля для каждого модуля. Если объявляется пространство имен, эти модули являются частью внешнего пространства имен. Если пространство имен не объявлено, модули становятся частью неявно созданного модуля верхнего уровня. В следующем примере кода показан файл кода, который содержит несколько модулей. Компилятор неявно создает модуль верхнего уровня с именем `Multiplemodules`, и `MyModule1` и `MyModule2` являются вложенными в этого модуля.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

При наличии нескольких файлов в проекте или в одной компиляции, или при создании библиотеки, необходимо включить объявления пространства имен или объявление модуля в верхней части файла. Компилятор F # определяет только имя модуля неявно при возникновении только один файл в командной строке, проекта или компиляции, и вы создаете приложение.

*Модификатор доступа* может принимать одно из следующих действий: `public`, `private`, `internal`. Дополнительные сведения см. в статье [Управление доступом](access-control.md). Значение по умолчанию — "public" (открытый).


## <a name="referencing-code-in-modules"></a>Ссылки на код в модулях
При создании ссылки функции, типы и значения из другого модуля необходимо использовать полное имя или открыть модуль. Если используется полное имя, необходимо указать пространства имен, модуля и идентификатор для нужный элемент программы. Разделить все компоненты полный путь с точкой (.), следующим образом.

`Namespace1.Namespace2.ModuleName.Identifier`

Можно открыть модуль или одно или несколько пространств имен для упрощения кода. Дополнительные сведения об открытии пространств имен и модулей см. в разделе [объявления импорта: `open` ключевое слово](import-declarations-the-open-keyword.md).

В следующем примере кода показан модуль верхнего уровня, который содержит весь код в конец файла.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Чтобы использовать этот код из другого файла, в том же проекте, затем использовать полные имена или открыть модуль перед использованием функции, как показано в следующих примерах.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Вложенные модули
Модули могут быть вложенными. Внутренние модули должен иметь отступ относительно внешних модулей указывает, что они внутренних модулей не новые модули. Например Сравните следующие два примера. Модуль `Z` является внутренним модулем в следующем коде.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Но модуль `Z` является одноуровневым модуль `Y` в следующем коде.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Модуль `Z` находится также на одном уровне в следующем коде, поскольку на него нет отступа по сравнению с другими объявлениями в модуле `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Наконец, если внешний модуль не содержит объявлений, а затем немедленно объявление другого модуля, предполагается, что новое объявление модуля является внутренним, но компилятор выдает предупреждение, если во втором определении модуля без отступа farther чем первый.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Чтобы устранить предупреждение, отступ внутренний модуль.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Если требуется, весь код в файл в один внешний модуль и требуется внутренние модули, внешний модуль не требует знака равенства, а объявления, включая объявления внутренних модулей, которые помещаются во внешний модуль не нужно иметь отступ. Объявления внутри внутренних модулей должны иметь отступы. В следующем коде показано в данном случае.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="module-rec-allowing-mutual-recursive-code-at-the-module-level"></a>Модуль `rec`: взаимной рекурсивные программного кода на уровне модуля

4.1 F # вводится понятие модулей, позволяющих все автономные кода взаимно рекурсивные.  Это выполняется через `module rec`.  Использование `module rec` можно устранить некоторые усилия невозможности писать код взаимно ссылочной между типами и модулей.  Ниже приведен пример этого:

```fsharp
module rec RecursiveModule =
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

    module private BananaHelpers =
        let peel (b : Banana) =
            let flip banana =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides banana =
                for side in banana.Sides do
                    if side = Unpeeled then
                        side <- Peeled

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.  Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.  Это будет невозможно выразить в F #, если вы удалили `rec` ключевое слово из `RecursiveModule` модуля.

Эта возможность, также возможна в [пространства имен](namespaces.md) с версии 4.1 F #.

## <a name="see-also"></a>См. также

[Справочник по языку F #](index.md)
[пространства имен](namespaces.md)
[F # 1009-FS RFC - разрешить взаимно ссылочные типы и модули через большего пространства в файлах](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
