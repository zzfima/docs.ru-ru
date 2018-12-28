---
title: Пространства имен
description: Узнайте, как F# пространства имен позволяет упорядочить код по областям соответствующей функциональности, предоставляя возможность присоединить имя к группированию элементов программы.
ms.date: 12/08/2018
ms.openlocfilehash: 526d7a07e4804751811c15fa91b0c74c1954d591
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613444"
---
# <a name="namespaces"></a><span data-ttu-id="11749-103">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="11749-103">Namespaces</span></span>

<span data-ttu-id="11749-104">Пространство имен позволяет упорядочить код по областям соответствующей функциональности, предоставляя возможность присоединить к группе имя F# программным элементам.</span><span class="sxs-lookup"><span data-stu-id="11749-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="11749-105">Пространства имен являются элементы обычно верхнего уровня в F# файлов.</span><span class="sxs-lookup"><span data-stu-id="11749-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="11749-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11749-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="11749-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="11749-107">Remarks</span></span>

<span data-ttu-id="11749-108">Если вы хотите поместить код в пространстве имен, первого объявления в файле необходимо объявить пространство имен.</span><span class="sxs-lookup"><span data-stu-id="11749-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="11749-109">Содержимое затем весь файл становятся частью пространства имен, если нет других объявление пространства имен существует последующих файла.</span><span class="sxs-lookup"><span data-stu-id="11749-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="11749-110">Если это так, в пространство имен первого считается весь код вплоть до следующего объявления пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="11749-111">Пространства имен не может непосредственно содержат значения и функции.</span><span class="sxs-lookup"><span data-stu-id="11749-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="11749-112">Вместо этого значения и функции должны быть включены в модули и модули, включаются в пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="11749-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="11749-113">Пространства имен может содержать типы, модули.</span><span class="sxs-lookup"><span data-stu-id="11749-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="11749-114">Комментарии XML-документа могут быть объявлены выше пространства имен, но они все игнорируются.</span><span class="sxs-lookup"><span data-stu-id="11749-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="11749-115">Директивы компилятора также могут быть объявлены выше пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="11749-116">Пространства имен может быть объявлен явным образом с помощью ключевого слова пространства имен или неявно при объявлении модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="11749-117">Чтобы объявить пространство имен явно, используйте ключевое слово namespace, за которым следует имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="11749-118">В примере показан файл кода, объявляющий пространство имен `Widgets` с типом и модуль, включенный в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="11749-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="11749-119">Если все содержимое файла находятся в одном модуле, можно также объявить пространства имен неявно с помощью `module` ключевое слово и имя нового пространства имен в полное имя модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="11749-120">В примере показан файл кода, объявляющий пространство имен `Widgets` и модуль `WidgetsModule`, содержащего функцию.</span><span class="sxs-lookup"><span data-stu-id="11749-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="11749-121">Следующий код эквивалентен предыдущему коду, но модуль является объявление локального модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="11749-122">В этом случае пространство имен должно отображаться на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="11749-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="11749-123">Если требуется несколько модулей в тот же файл в один или несколько пространств имен, необходимо использовать объявления локального модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="11749-124">При использовании локального модуля объявления, в объявлениях модуля нельзя использовать имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="11749-125">Ниже приведен файл, содержащий объявление пространства имен и два объявления локального модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="11749-126">В этом случае модули содержатся непосредственно в пространстве имен; Нет не неявно созданного модуля, который имеет то же имя, что и файл.</span><span class="sxs-lookup"><span data-stu-id="11749-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="11749-127">Любой другой код в файле, такие как `do` привязки, — в пространстве имен, но не в внутренних модулей, поэтому необходимо уточнить член модуля `widgetFunction` , используя имя модуля.</span><span class="sxs-lookup"><span data-stu-id="11749-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="11749-128">Выходные данные этого примера выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="11749-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="11749-129">Дополнительные сведения см. в разделе [модули](modules.md).</span><span class="sxs-lookup"><span data-stu-id="11749-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="11749-130">Вложенные пространства имен</span><span class="sxs-lookup"><span data-stu-id="11749-130">Nested Namespaces</span></span>

<span data-ttu-id="11749-131">При создании вложенного пространства имен, необходимо полностью указать его.</span><span class="sxs-lookup"><span data-stu-id="11749-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="11749-132">В противном случае можно создать новое пространство имен верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="11749-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="11749-133">Отступ игнорируется в объявлениях пространств имен.</span><span class="sxs-lookup"><span data-stu-id="11749-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="11749-134">В следующем примере показан способ объявления вложенного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="11749-135">Пространства имен в файлы и сборки</span><span class="sxs-lookup"><span data-stu-id="11749-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="11749-136">Пространства имен может охватывать несколько файлов проекта или компиляции.</span><span class="sxs-lookup"><span data-stu-id="11749-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="11749-137">Термин *фрагмент пространства имен* описывает часть пространства имен, которое включено в один файл.</span><span class="sxs-lookup"><span data-stu-id="11749-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="11749-138">Пространства имен также могут охватывать несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="11749-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="11749-139">Например `System` пространство имен включает всей .NET Framework, которая охватывает несколько сборок и содержит много вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="11749-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="11749-140">Глобальное пространство имен</span><span class="sxs-lookup"><span data-stu-id="11749-140">Global Namespace</span></span>

<span data-ttu-id="11749-141">Используйте стандартные пространства имен `global` поместить имена в пространство имен верхнего уровня .NET.</span><span class="sxs-lookup"><span data-stu-id="11749-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="11749-142">Можно также использовать глобальный для ссылки на пространство имен .NET верхнего уровня, например, чтобы устранить конфликты имен с другими пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="11749-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="11749-143">Рекурсивные пространств имен</span><span class="sxs-lookup"><span data-stu-id="11749-143">Recursive namespaces</span></span>

<span data-ttu-id="11749-144">Пространства имен также могут объявляться как рекурсивный, чтобы разрешить все автономной кода взаимно рекурсивные.</span><span class="sxs-lookup"><span data-stu-id="11749-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="11749-145">Это делается с помощью `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="11749-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="11749-146">Использование `namespace rec` могут помочь в решении некоторые трудности в не возможность написания кода в взаимно ссылочные типы и модули.</span><span class="sxs-lookup"><span data-stu-id="11749-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="11749-147">Ниже приведен пример этого:</span><span class="sxs-lookup"><span data-stu-id="11749-147">The following is an example of this:</span></span>

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

<span data-ttu-id="11749-148">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="11749-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="11749-149">Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="11749-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="11749-150">Это было бы невозможно выразить в F# Если вы удалили `rec` ключевое слово from `MutualReferences` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="11749-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="11749-151">Эта функция также доступна для верхнего уровня [модули](modules.md).</span><span class="sxs-lookup"><span data-stu-id="11749-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11749-152">См. также</span><span class="sxs-lookup"><span data-stu-id="11749-152">See also</span></span>

- [<span data-ttu-id="11749-153">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="11749-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="11749-154">Модули</span><span class="sxs-lookup"><span data-stu-id="11749-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="11749-155">F#RFC-FS-1009 - разрешить взаимно ссылочные типы и модули через большего пространства в файлах</span><span class="sxs-lookup"><span data-stu-id="11749-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)