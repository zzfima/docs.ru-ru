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
# <a name="modules"></a><span data-ttu-id="4e60d-104">Модули</span><span class="sxs-lookup"><span data-stu-id="4e60d-104">Modules</span></span>

<span data-ttu-id="4e60d-105">В контексте языка F # *модуль* — это группирование кода F #, например значений, типов и значений функций, в программе F #.</span><span class="sxs-lookup"><span data-stu-id="4e60d-105">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="4e60d-106">Код группирования в модулях объединяет связанный код и помогает избежать конфликтов имен в программе.</span><span class="sxs-lookup"><span data-stu-id="4e60d-106">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e60d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e60d-107">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="4e60d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e60d-108">Remarks</span></span>
<span data-ttu-id="4e60d-109">Модуль F # — это группирование конструкций кода F #, например типов, значений, значений функций и кода в `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="4e60d-109">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="4e60d-110">Он реализован в виде общего класса среды выполнения (CLR) языка, содержит только статические члены.</span><span class="sxs-lookup"><span data-stu-id="4e60d-110">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="4e60d-111">Существует два типа объявлений модулей, в зависимости от того, включен ли в модуль файл целиком: объявление модуля верхнего уровня и объявление локального модуля.</span><span class="sxs-lookup"><span data-stu-id="4e60d-111">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="4e60d-112">Объявление модуля верхнего уровня содержит весь файл в модуле.</span><span class="sxs-lookup"><span data-stu-id="4e60d-112">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="4e60d-113">Объявление модуля верхнего уровня может появиться только как первого объявления в файле.</span><span class="sxs-lookup"><span data-stu-id="4e60d-113">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="4e60d-114">В синтаксисе объявления модуля верхнего уровня, необязательные *полное пространство имен* последовательность вложенных имен пространств имен, содержащую модуль.</span><span class="sxs-lookup"><span data-stu-id="4e60d-114">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="4e60d-115">Полное имя пространства имен не требуется быть ранее объявлено.</span><span class="sxs-lookup"><span data-stu-id="4e60d-115">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="4e60d-116">Необходимо отступы при объявлении модуля верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="4e60d-116">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="4e60d-117">Вы имеете расстановка отступов во всем объявлениям в локальные модули.</span><span class="sxs-lookup"><span data-stu-id="4e60d-117">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="4e60d-118">В объявлении локального модуля только объявления, отображаются с отступом внутри объявления являются частью этого модуля.</span><span class="sxs-lookup"><span data-stu-id="4e60d-118">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="4e60d-119">Если файл с кодом не начинается с объявления модуля верхнего уровня или объявление пространства имен, все содержимое файла, включая все локальные модули, становится частью неявно созданного модуля верхнего уровня, который имеет то же имя, что и файл без расширения, с первой буквой, переведенную в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="4e60d-119">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="4e60d-120">Например рассмотрим следующий файл.</span><span class="sxs-lookup"><span data-stu-id="4e60d-120">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="4e60d-121">Этот файл будет скомпилирован, как если бы он был оформлен таким образом:</span><span class="sxs-lookup"><span data-stu-id="4e60d-121">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="4e60d-122">Если в файле имеется несколько модулей, необходимо использовать объявление локального модуля для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="4e60d-122">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="4e60d-123">Если объявляется пространство имен, эти модули являются частью внешнего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="4e60d-123">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="4e60d-124">Если пространство имен не объявлено, модули становятся частью неявно созданного модуля верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="4e60d-124">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="4e60d-125">В следующем примере кода показан файл кода, который содержит несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="4e60d-125">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="4e60d-126">Компилятор неявно создает модуль верхнего уровня с именем `Multiplemodules`, и `MyModule1` и `MyModule2` являются вложенными в этого модуля.</span><span class="sxs-lookup"><span data-stu-id="4e60d-126">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="4e60d-127">При наличии нескольких файлов в проекте или в одной компиляции, или при создании библиотеки, необходимо включить объявления пространства имен или объявление модуля в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="4e60d-127">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="4e60d-128">Компилятор F # определяет только имя модуля неявно при возникновении только один файл в командной строке, проекта или компиляции, и вы создаете приложение.</span><span class="sxs-lookup"><span data-stu-id="4e60d-128">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="4e60d-129">*Модификатор доступа* может принимать одно из следующих действий: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="4e60d-129">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="4e60d-130">Дополнительные сведения см. в статье [Управление доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="4e60d-130">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="4e60d-131">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="4e60d-131">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="4e60d-132">Ссылки на код в модулях</span><span class="sxs-lookup"><span data-stu-id="4e60d-132">Referencing Code in Modules</span></span>
<span data-ttu-id="4e60d-133">При создании ссылки функции, типы и значения из другого модуля необходимо использовать полное имя или открыть модуль.</span><span class="sxs-lookup"><span data-stu-id="4e60d-133">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="4e60d-134">Если используется полное имя, необходимо указать пространства имен, модуля и идентификатор для нужный элемент программы.</span><span class="sxs-lookup"><span data-stu-id="4e60d-134">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="4e60d-135">Разделить все компоненты полный путь с точкой (.), следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4e60d-135">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="4e60d-136">Можно открыть модуль или одно или несколько пространств имен для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="4e60d-136">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="4e60d-137">Дополнительные сведения об открытии пространств имен и модулей см. в разделе [объявления импорта: `open` ключевое слово](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="4e60d-137">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="4e60d-138">В следующем примере кода показан модуль верхнего уровня, который содержит весь код в конец файла.</span><span class="sxs-lookup"><span data-stu-id="4e60d-138">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="4e60d-139">Чтобы использовать этот код из другого файла, в том же проекте, затем использовать полные имена или открыть модуль перед использованием функции, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="4e60d-139">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="4e60d-140">Вложенные модули</span><span class="sxs-lookup"><span data-stu-id="4e60d-140">Nested Modules</span></span>
<span data-ttu-id="4e60d-141">Модули могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="4e60d-141">Modules can be nested.</span></span> <span data-ttu-id="4e60d-142">Внутренние модули должен иметь отступ относительно внешних модулей указывает, что они внутренних модулей не новые модули.</span><span class="sxs-lookup"><span data-stu-id="4e60d-142">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="4e60d-143">Например Сравните следующие два примера.</span><span class="sxs-lookup"><span data-stu-id="4e60d-143">For example, compare the following two examples.</span></span> <span data-ttu-id="4e60d-144">Модуль `Z` является внутренним модулем в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4e60d-144">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="4e60d-145">Но модуль `Z` является одноуровневым модуль `Y` в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4e60d-145">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="4e60d-146">Модуль `Z` находится также на одном уровне в следующем коде, поскольку на него нет отступа по сравнению с другими объявлениями в модуле `Y`.</span><span class="sxs-lookup"><span data-stu-id="4e60d-146">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="4e60d-147">Наконец, если внешний модуль не содержит объявлений, а затем немедленно объявление другого модуля, предполагается, что новое объявление модуля является внутренним, но компилятор выдает предупреждение, если во втором определении модуля без отступа farther чем первый.</span><span class="sxs-lookup"><span data-stu-id="4e60d-147">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="4e60d-148">Чтобы устранить предупреждение, отступ внутренний модуль.</span><span class="sxs-lookup"><span data-stu-id="4e60d-148">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="4e60d-149">Если требуется, весь код в файл в один внешний модуль и требуется внутренние модули, внешний модуль не требует знака равенства, а объявления, включая объявления внутренних модулей, которые помещаются во внешний модуль не нужно иметь отступ.</span><span class="sxs-lookup"><span data-stu-id="4e60d-149">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="4e60d-150">Объявления внутри внутренних модулей должны иметь отступы.</span><span class="sxs-lookup"><span data-stu-id="4e60d-150">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="4e60d-151">В следующем коде показано в данном случае.</span><span class="sxs-lookup"><span data-stu-id="4e60d-151">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="module-rec-allowing-mutual-recursive-code-at-the-module-level"></a><span data-ttu-id="4e60d-152">Модуль `rec`: взаимной рекурсивные программного кода на уровне модуля</span><span class="sxs-lookup"><span data-stu-id="4e60d-152">Module `rec`: allowing mutual recursive code at the module level</span></span>

<span data-ttu-id="4e60d-153">4.1 F # вводится понятие модулей, позволяющих все автономные кода взаимно рекурсивные.</span><span class="sxs-lookup"><span data-stu-id="4e60d-153">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="4e60d-154">Это выполняется через `module rec`.</span><span class="sxs-lookup"><span data-stu-id="4e60d-154">This is done via `module rec`.</span></span>  <span data-ttu-id="4e60d-155">Использование `module rec` можно устранить некоторые усилия невозможности писать код взаимно ссылочной между типами и модулей.</span><span class="sxs-lookup"><span data-stu-id="4e60d-155">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="4e60d-156">Ниже приведен пример этого:</span><span class="sxs-lookup"><span data-stu-id="4e60d-156">The following is an example of this:</span></span>

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

<span data-ttu-id="4e60d-157">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="4e60d-157">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="4e60d-158">Кроме того, модуль `BananaHelpers` и класс `Banana` также обращаются друг к другу.</span><span class="sxs-lookup"><span data-stu-id="4e60d-158">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="4e60d-159">Это будет невозможно выразить в F #, если вы удалили `rec` ключевое слово из `RecursiveModule` модуля.</span><span class="sxs-lookup"><span data-stu-id="4e60d-159">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="4e60d-160">Эта возможность, также возможна в [пространства имен](namespaces.md) с версии 4.1 F #.</span><span class="sxs-lookup"><span data-stu-id="4e60d-160">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e60d-161">См. также</span><span class="sxs-lookup"><span data-stu-id="4e60d-161">See Also</span></span>

<span data-ttu-id="4e60d-162">[Справочник по языку F #](index.md)
[пространства имен](namespaces.md)
[F # 1009-FS RFC - разрешить взаимно ссылочные типы и модули через большего пространства в файлах](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span><span class="sxs-lookup"><span data-stu-id="4e60d-162">[F# Language Reference](index.md)
[Namespaces](namespaces.md)
[F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span></span>
