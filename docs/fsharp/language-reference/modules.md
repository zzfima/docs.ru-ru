---
title: Модули
description: Узнайте, как F# модуль — это группа F# кодов, таких как значения, типы и значения функции, в F# программы.
ms.date: 04/24/2017
ms.openlocfilehash: 9e5bef4ffe3301a69bbe32483625652d988f8a35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666322"
---
# <a name="modules"></a><span data-ttu-id="d3e64-103">Модули</span><span class="sxs-lookup"><span data-stu-id="d3e64-103">Modules</span></span>

<span data-ttu-id="d3e64-104">В контексте F# языка, *модуль* — это группа F# кодов, таких как значения, типы и значения функции, в F# программы.</span><span class="sxs-lookup"><span data-stu-id="d3e64-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="d3e64-105">Код группирования в модулях объединяет связанный код и помогает избежать конфликтов имен в программе.</span><span class="sxs-lookup"><span data-stu-id="d3e64-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3e64-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3e64-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="d3e64-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3e64-107">Remarks</span></span>

<span data-ttu-id="d3e64-108">F# Модуль — это группа F# код конструкций, таких как типы, значений, значений функций и кода в `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="d3e64-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="d3e64-109">Он реализуется как общий класс языковой среды выполнения (CLR), содержит только статические члены.</span><span class="sxs-lookup"><span data-stu-id="d3e64-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="d3e64-110">Существует два типа объявлений модулей, в зависимости от того, включены ли весь файл целиком в модуле: объявление модуля верхнего уровня и объявление локального модуля.</span><span class="sxs-lookup"><span data-stu-id="d3e64-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="d3e64-111">Объявление модуля верхнего уровня содержит весь файл целиком в модуле.</span><span class="sxs-lookup"><span data-stu-id="d3e64-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="d3e64-112">Объявление модуля верхнего уровня может отображаться только в качестве первого объявления в файле.</span><span class="sxs-lookup"><span data-stu-id="d3e64-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="d3e64-113">В синтаксисе объявления верхнего уровня модуля, необязательный *доменное пространство имен* последовательность вложенных имен пространств имен, содержащего модуль.</span><span class="sxs-lookup"><span data-stu-id="d3e64-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="d3e64-114">Имя пространства имен не нужно предварительно объявлять.</span><span class="sxs-lookup"><span data-stu-id="d3e64-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="d3e64-115">У вас нет отступа объявления в модуль верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d3e64-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="d3e64-116">У вас отступ для всех объявлений локальных модулей.</span><span class="sxs-lookup"><span data-stu-id="d3e64-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="d3e64-117">В объявлении локального модуля только объявления, которые отображаются с отступом внутри объявления являются частью этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d3e64-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="d3e64-118">Если файл с кодом не начинается с объявления модуля верхнего уровня или объявление пространства имен, все содержимое файла, включая все локальные модули, становится частью неявно созданного модуля верхнего уровня, который имеет то же имя файла, без расширения с первой буквой, переведенную в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="d3e64-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="d3e64-119">Например рассмотрим следующий файл.</span><span class="sxs-lookup"><span data-stu-id="d3e64-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="d3e64-120">Этот файл компилируется так, как если бы он был оформлен таким образом:</span><span class="sxs-lookup"><span data-stu-id="d3e64-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="d3e64-121">Если у вас есть несколько модулей в файле, необходимо использовать объявление локального модуля для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="d3e64-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="d3e64-122">Если объявляется пространство имен, эти модули являются частью вложенное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d3e64-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="d3e64-123">Если пространство имен не объявлен, модули становятся частью неявно созданного модуля верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d3e64-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="d3e64-124">В следующем примере кода показан файл кода, содержащий несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="d3e64-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="d3e64-125">Компилятор неявно создает модуль верхнего уровня с именем `Multiplemodules`, и `MyModule1` и `MyModule2` вложены в этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d3e64-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="d3e64-126">Если у вас есть несколько файлов в проекте или в рамках одной процедуры компиляции, или если вы создаете библиотеку, необходимо включить объявление пространства имен или модуля в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="d3e64-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="d3e64-127">F# Компилятора только определяет имя модуля неявно при имеется только один файл в командной строке, проекта или компиляции, и при создании приложения.</span><span class="sxs-lookup"><span data-stu-id="d3e64-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="d3e64-128">*Модификатор доступа* может принимать одно из следующих: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="d3e64-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="d3e64-129">Дополнительные сведения см. в статье [Управление доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="d3e64-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="d3e64-130">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="d3e64-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="d3e64-131">Ссылки на код в модулях</span><span class="sxs-lookup"><span data-stu-id="d3e64-131">Referencing Code in Modules</span></span>

<span data-ttu-id="d3e64-132">При создании ссылки функции, типы и значения из другого модуля, необходимо использовать полное имя или открыть модуль.</span><span class="sxs-lookup"><span data-stu-id="d3e64-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="d3e64-133">Если вы используете полное имя, необходимо указать пространства имен, модуля и идентификатор нужный элемент программы.</span><span class="sxs-lookup"><span data-stu-id="d3e64-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="d3e64-134">Разделите каждую часть полный путь с точкой (.), следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d3e64-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="d3e64-135">Можно открыть модуль или одно или несколько пространств имен для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="d3e64-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="d3e64-136">Дополнительные сведения об открытии пространств имен и модулей см. в разделе [объявления импорта: `open` Ключевое слово](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="d3e64-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="d3e64-137">В следующем примере кода показан модуль верхнего уровня, который содержит весь код в конец файла.</span><span class="sxs-lookup"><span data-stu-id="d3e64-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="d3e64-138">Чтобы использовать этот код из другого файла, в том же проекте, можно использовать полные имена или открыть модуль перед использованием функции, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="d3e64-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="d3e64-139">Вложенные модули</span><span class="sxs-lookup"><span data-stu-id="d3e64-139">Nested Modules</span></span>

<span data-ttu-id="d3e64-140">Модули могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="d3e64-140">Modules can be nested.</span></span> <span data-ttu-id="d3e64-141">Внутренние модули должны иметь отступ относительно внешних модулей для указания, что они внутренних модулей, а не новые модули.</span><span class="sxs-lookup"><span data-stu-id="d3e64-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="d3e64-142">Например Сравните следующие два примера.</span><span class="sxs-lookup"><span data-stu-id="d3e64-142">For example, compare the following two examples.</span></span> <span data-ttu-id="d3e64-143">Модуль `Z` представляет собой внутренний модуль, в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d3e64-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="d3e64-144">Но модуль `Z` является родственным модуль `Y` в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d3e64-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="d3e64-145">Модуль `Z` находится также на одном уровне в следующем коде, так как для него нет отступа по сравнению с другими объявлениями в модуле `Y`.</span><span class="sxs-lookup"><span data-stu-id="d3e64-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="d3e64-146">Наконец, если внешний модуль не содержит объявлений и сразу же следует объявление другой модуль, предполагается, что новые объявления модуля является внутренним, но, компилятор выдает предупреждение, если второе определение модуля отобразится без отступа farther чем первый.</span><span class="sxs-lookup"><span data-stu-id="d3e64-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="d3e64-147">Чтобы устранить предупреждение, добавьте отступ внутренний модуль.</span><span class="sxs-lookup"><span data-stu-id="d3e64-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="d3e64-148">Если требуется, чтобы весь код в файл, который требуется в один внешний модуль, и вы хотите внутренних модулей, внешний модуль не требуется знак равенства и объявления, включая объявления внутренних модулей, которые помещаются во внешний модуль не требуется иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="d3e64-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="d3e64-149">Объявления внутри внутренних модулей должны иметь отступы.</span><span class="sxs-lookup"><span data-stu-id="d3e64-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="d3e64-150">В следующем коде показано в данном случае.</span><span class="sxs-lookup"><span data-stu-id="d3e64-150">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="d3e64-151">Рекурсивные модулей</span><span class="sxs-lookup"><span data-stu-id="d3e64-151">Recursive modules</span></span>

<span data-ttu-id="d3e64-152">F#4.1, вводится понятие модулей, позволяющих все автономной кода взаимно рекурсивные.</span><span class="sxs-lookup"><span data-stu-id="d3e64-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="d3e64-153">Это делается с помощью `module rec`.</span><span class="sxs-lookup"><span data-stu-id="d3e64-153">This is done via `module rec`.</span></span>  <span data-ttu-id="d3e64-154">Использование `module rec` могут помочь в решении некоторые трудности в не возможность написания кода в взаимно ссылочные типы и модули.</span><span class="sxs-lookup"><span data-stu-id="d3e64-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="d3e64-155">Ниже приведен пример этого:</span><span class="sxs-lookup"><span data-stu-id="d3e64-155">The following is an example of this:</span></span>

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

<span data-ttu-id="d3e64-156">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="d3e64-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="d3e64-157">Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="d3e64-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="d3e64-158">Это не позволяет выражать в F# Если вы удалили `rec` ключевое слово from `RecursiveModule` модуля.</span><span class="sxs-lookup"><span data-stu-id="d3e64-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="d3e64-159">Эта возможность также возможен в [пространства имен](namespaces.md) с F# 4.1.</span><span class="sxs-lookup"><span data-stu-id="d3e64-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3e64-160">См. также</span><span class="sxs-lookup"><span data-stu-id="d3e64-160">See also</span></span>

- [<span data-ttu-id="d3e64-161">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="d3e64-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d3e64-162">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="d3e64-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="d3e64-163">F#RFC-FS-1009 - разрешить взаимно ссылочные типы и модули через большего пространства в файлах</span><span class="sxs-lookup"><span data-stu-id="d3e64-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)