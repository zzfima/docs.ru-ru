---
title: Пространства имен (F#)
description: 'Узнайте, как пространство имен F # позволяет упорядочить код по областям соответствующей функциональности, предоставляя возможность присоединить имя к группированию элементов программы.'
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178263"
---
# <a name="namespaces"></a><span data-ttu-id="0d1b5-103">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="0d1b5-103">Namespaces</span></span>

<span data-ttu-id="0d1b5-104">С помощью пространства имен вы можете упорядочить код по областям соответствующей функциональности, подключив имя к группированию элементов программы.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d1b5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d1b5-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="0d1b5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d1b5-106">Remarks</span></span>

<span data-ttu-id="0d1b5-107">Если вы хотите поместить код в пространстве имен, первого объявления в файле необходимо объявить пространство имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="0d1b5-108">Содержимое этого файла становится частью пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="0d1b5-109">Пространства имен не может непосредственно содержат значения и функции.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="0d1b5-110">Вместо этого значения и функции должны быть включены в модули и модули, включаются в пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="0d1b5-111">Пространства имен может содержать типы, модули.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="0d1b5-112">Пространства имен может быть объявлен явным образом с помощью ключевого слова пространства имен или неявно при объявлении модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="0d1b5-113">Чтобы объявить пространство имен явно, используйте ключевое слово namespace, за которым следует имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="0d1b5-114">Следующий пример показывает файл кода, объявляющий пространство имен мини-приложения с типом и модуль, включенный в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="0d1b5-115">Если все содержимое файла находятся в одном модуле, можно также объявить пространства имен неявно с помощью `module` ключевое слово и имя нового пространства имен в полное имя модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="0d1b5-116">В примере показан файл кода, объявляющий пространство имен `Widgets` и модуль `WidgetsModule`, содержащего функцию.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="0d1b5-117">Следующий код эквивалентен предыдущему коду, но модуль является объявление локального модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="0d1b5-118">В этом случае пространство имен должно отображаться на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="0d1b5-119">Если требуется несколько модулей в тот же файл в один или несколько пространств имен, необходимо использовать объявления локального модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="0d1b5-120">При использовании локального модуля объявления, в объявлениях модуля нельзя использовать имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="0d1b5-121">Ниже приведен файл, содержащий объявление пространства имен и два объявления локального модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="0d1b5-122">В этом случае модули содержатся непосредственно в пространстве имен; Нет не неявно созданного модуля, который имеет то же имя, что и файл.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="0d1b5-123">Любой другой код в файле, такие как `do` привязки, — в пространстве имен, но не в внутренних модулей, поэтому необходимо уточнить член модуля `widgetFunction` , используя имя модуля.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="0d1b5-124">Выходные данные этого примера выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="0d1b5-125">Дополнительные сведения см. в разделе [модули](modules.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b5-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="0d1b5-126">Вложенные пространства имен</span><span class="sxs-lookup"><span data-stu-id="0d1b5-126">Nested Namespaces</span></span>

<span data-ttu-id="0d1b5-127">При создании вложенного пространства имен, необходимо полностью указать его.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="0d1b5-128">В противном случае можно создать новое пространство имен верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="0d1b5-129">Отступ игнорируется в объявлениях пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="0d1b5-130">В следующем примере показан способ объявления вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="0d1b5-131">Пространства имен в файлы и сборки</span><span class="sxs-lookup"><span data-stu-id="0d1b5-131">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="0d1b5-132">Пространства имен может охватывать несколько файлов проекта или компиляции.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="0d1b5-133">Термин *фрагмент пространства имен* описывает часть пространства имен, которое включено в один файл.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="0d1b5-134">Пространства имен также могут охватывать несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="0d1b5-135">Например `System` пространство имен включает всей .NET Framework, которая охватывает несколько сборок и содержит много вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="0d1b5-136">Глобальное пространство имен</span><span class="sxs-lookup"><span data-stu-id="0d1b5-136">Global Namespace</span></span>

<span data-ttu-id="0d1b5-137">Используйте стандартные пространства имен `global` поместить имена в пространство имен верхнего уровня .NET.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="0d1b5-138">Можно также использовать глобальный для ссылки на пространство имен .NET верхнего уровня, например, чтобы устранить конфликты имен с другими пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="0d1b5-139">Рекурсивные пространств имен</span><span class="sxs-lookup"><span data-stu-id="0d1b5-139">Recursive namespaces</span></span>

<span data-ttu-id="0d1b5-140">F # 4.1, вводится понятие пространств имен, которая допускает все автономной кода взаимно рекурсивные.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="0d1b5-141">Это делается с помощью `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="0d1b5-142">Использование `namespace rec` могут помочь в решении некоторые трудности в не возможность написания кода в взаимно ссылочные типы и модули.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="0d1b5-143">Ниже приведен пример этого:</span><span class="sxs-lookup"><span data-stu-id="0d1b5-143">The following is an example of this:</span></span>

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

<span data-ttu-id="0d1b5-144">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="0d1b5-145">Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="0d1b5-146">Это не позволяет выражать в F #, если вы удалили `rec` ключевое слово from `MutualReferences` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="0d1b5-147">Эта функция также доступна для верхнего уровня [модули](modules.md) в F # 4.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0d1b5-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d1b5-148">См. также</span><span class="sxs-lookup"><span data-stu-id="0d1b5-148">See also</span></span>

- [<span data-ttu-id="0d1b5-149">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="0d1b5-149">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0d1b5-150">Модули</span><span class="sxs-lookup"><span data-stu-id="0d1b5-150">Modules</span></span>](modules.md)
- [<span data-ttu-id="0d1b5-151">F # RFC FS-1009 - разрешить взаимно ссылочные типы и модули через большего пространства в файлах</span><span class="sxs-lookup"><span data-stu-id="0d1b5-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
