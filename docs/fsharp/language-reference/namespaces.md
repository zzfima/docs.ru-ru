---
title: Пространства имен
description: Сведения о том F# , как пространство имен позволяет организовать код в области связанных функций, позволяя присоединить имя к группированию элементов программы.
ms.date: 12/08/2018
ms.openlocfilehash: a55da1592b04c64576b4c66de61b5ca137289a6f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425049"
---
# <a name="namespaces"></a><span data-ttu-id="b2498-103">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="b2498-103">Namespaces</span></span>

<span data-ttu-id="b2498-104">Пространство имен позволяет организовать код в области связанных функций, позволяя присоединить имя к группированию элементов F# программы.</span><span class="sxs-lookup"><span data-stu-id="b2498-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="b2498-105">Пространства имен обычно являются элементами верхнего уровня в F# файлах.</span><span class="sxs-lookup"><span data-stu-id="b2498-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2498-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2498-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="b2498-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2498-107">Remarks</span></span>

<span data-ttu-id="b2498-108">Если вы хотите поместить код в пространство имен, первое объявление в файле должно объявлять пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="b2498-109">Содержимое всего файла затем становится частью пространства имен, если другое объявление пространств имен не существует в файле.</span><span class="sxs-lookup"><span data-stu-id="b2498-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="b2498-110">В этом случае весь код наследуется до тех пор, пока следующее объявление пространства имен не станет частью первого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="b2498-111">Пространства имен не могут содержать непосредственно значения и функции.</span><span class="sxs-lookup"><span data-stu-id="b2498-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="b2498-112">Вместо этого значения и функции должны включаться в модули, а модули включаются в пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="b2498-113">Пространства имен могут содержать типы, модули.</span><span class="sxs-lookup"><span data-stu-id="b2498-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="b2498-114">Комментарии XML doc можно объявить над пространством имен, но они не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b2498-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="b2498-115">Директивы компилятора также можно объявить над пространством имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="b2498-116">Пространства имен могут быть объявлены явно с помощью ключевого слова namespace или неявно при объявлении модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="b2498-117">Чтобы объявить пространство имен явным образом, используйте ключевое слово namespace, за которым следует имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="b2498-118">В следующем примере показан файл кода, в котором объявляется пространство имен `Widgets` с типом и модулем, входящим в это пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="b2498-119">Если все содержимое файла находится в одном модуле, можно также объявить пространства имен неявно, используя ключевое слово `module` и указав новое имя пространства имен в полном имени модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="b2498-120">В следующем примере показан файл кода, в котором объявляется пространство имен `Widgets` и модуль `WidgetsModule`, который содержит функцию.</span><span class="sxs-lookup"><span data-stu-id="b2498-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="b2498-121">Следующий код эквивалентен предыдущему коду, но модуль является объявлением локального модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="b2498-122">В этом случае пространство имен должно располагаться в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="b2498-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="b2498-123">Если в одном файле или нескольких пространствах имен требуется несколько модулей, необходимо использовать объявления локальных модулей.</span><span class="sxs-lookup"><span data-stu-id="b2498-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="b2498-124">При использовании объявлений локального модуля нельзя использовать полное пространство имен в объявлениях модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="b2498-125">В следующем коде показан файл с объявлением пространства имен и двумя объявлениями локального модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="b2498-126">В этом случае модули содержатся непосредственно в пространстве имен. не существует неявно созданного модуля, имя которого совпадает с именем файла.</span><span class="sxs-lookup"><span data-stu-id="b2498-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="b2498-127">Любой другой код в файле, например привязка `do`, находится в пространстве имен, но не во внутренних модулях, поэтому необходимо уточнить члена модуля `widgetFunction` с помощью имени модуля.</span><span class="sxs-lookup"><span data-stu-id="b2498-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="b2498-128">Выходные данные этого примера выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b2498-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="b2498-129">Дополнительные сведения см. в разделе [модули](modules.md).</span><span class="sxs-lookup"><span data-stu-id="b2498-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="b2498-130">Вложенные пространства имен</span><span class="sxs-lookup"><span data-stu-id="b2498-130">Nested Namespaces</span></span>

<span data-ttu-id="b2498-131">При создании вложенного пространства имен необходимо полностью уточнить его.</span><span class="sxs-lookup"><span data-stu-id="b2498-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="b2498-132">В противном случае создается новое пространство имен верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="b2498-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="b2498-133">Отступ не учитывается в объявлениях пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="b2498-134">В следующем примере показано, как объявить вложенное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="b2498-135">Пространства имен в файлах и сборках</span><span class="sxs-lookup"><span data-stu-id="b2498-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="b2498-136">Пространства имен могут охватывать несколько файлов в одном проекте или компиляции.</span><span class="sxs-lookup"><span data-stu-id="b2498-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="b2498-137">Фрагмент «термин *пространства имен* » описывает часть пространства имен, включенную в один файл.</span><span class="sxs-lookup"><span data-stu-id="b2498-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="b2498-138">Пространства имен могут также охватывать несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="b2498-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="b2498-139">Например, пространство имен `System` включает в себя весь .NET Framework, который охватывает множество сборок и содержит множество вложенных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="b2498-140">Глобальное пространство имен</span><span class="sxs-lookup"><span data-stu-id="b2498-140">Global Namespace</span></span>

<span data-ttu-id="b2498-141">Для размещения имен в пространстве имен .NET верхнего уровня используется предопределенное `global` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="b2498-142">Можно также использовать Global для ссылки на пространство имен .NET верхнего уровня, например, чтобы разрешить конфликты имен с другими пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="b2498-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="b2498-143">Рекурсивные пространства имен</span><span class="sxs-lookup"><span data-stu-id="b2498-143">Recursive namespaces</span></span>

<span data-ttu-id="b2498-144">Пространства имен также можно объявить как рекурсивные, чтобы обеспечить взаимную рекурсивную рекурсию для всего автономного кода.</span><span class="sxs-lookup"><span data-stu-id="b2498-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="b2498-145">Это выполняется с помощью `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="b2498-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="b2498-146">Использование `namespace rec` может сократить некоторые трудности, не позволяя писать взаимно ссылочный код между типами и модулями.</span><span class="sxs-lookup"><span data-stu-id="b2498-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="b2498-147">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="b2498-147">The following is an example of this:</span></span>

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

<span data-ttu-id="b2498-148">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба ссылаются друг на друга.</span><span class="sxs-lookup"><span data-stu-id="b2498-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="b2498-149">Кроме того, модуль `BananaHelpers` и класс `Banana` также ссылаются друг на друга.</span><span class="sxs-lookup"><span data-stu-id="b2498-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="b2498-150">Это было бы невозможно выразить в F# случае удаления ключевого слова `rec` из пространства имен `MutualReferences`.</span><span class="sxs-lookup"><span data-stu-id="b2498-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="b2498-151">Эта функция также доступна для [модулей](modules.md)верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="b2498-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2498-152">См. также</span><span class="sxs-lookup"><span data-stu-id="b2498-152">See also</span></span>

- [<span data-ttu-id="b2498-153">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="b2498-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b2498-154">Модули</span><span class="sxs-lookup"><span data-stu-id="b2498-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="b2498-155">F#RFC FS-1009 — разрешить взаимно ссылочные типы и модули в более крупных областях внутри файлов</span><span class="sxs-lookup"><span data-stu-id="b2498-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
