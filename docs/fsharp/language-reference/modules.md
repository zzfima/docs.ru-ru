---
title: Модули
description: Сведения о том F# , как модуль представляет собой F# Группирование кода, например значения, типы и значения функций, в F# программе.
ms.date: 04/24/2017
ms.openlocfilehash: fbde0c8b001d88614ba2de49c4aa7bfa098c6945
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425058"
---
# <a name="modules"></a><span data-ttu-id="bbed1-103">Модули</span><span class="sxs-lookup"><span data-stu-id="bbed1-103">Modules</span></span>

<span data-ttu-id="bbed1-104">В контексте F# языка *модуль* — это группа F# кода, например значения, типы и значения функций, в F# программе.</span><span class="sxs-lookup"><span data-stu-id="bbed1-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="bbed1-105">Код группирования в модулях объединяет связанный код и помогает избежать конфликтов имен в программе.</span><span class="sxs-lookup"><span data-stu-id="bbed1-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbed1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbed1-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="bbed1-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="bbed1-107">Remarks</span></span>

<span data-ttu-id="bbed1-108">F# Модуль — это группа конструкций F# кода, таких как типы, значения, значения функций и код в привязках `do`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="bbed1-109">Он реализуется как класс среды CLR, имеющий только статические члены.</span><span class="sxs-lookup"><span data-stu-id="bbed1-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="bbed1-110">Существует два типа объявлений модулей в зависимости от того, включен ли в модуль весь файл: объявление модуля верхнего уровня и объявление локального модуля.</span><span class="sxs-lookup"><span data-stu-id="bbed1-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="bbed1-111">Объявление модуля верхнего уровня включает в себя весь файл в модуле.</span><span class="sxs-lookup"><span data-stu-id="bbed1-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="bbed1-112">Объявление модуля верхнего уровня может использоваться только в качестве первого объявления в файле.</span><span class="sxs-lookup"><span data-stu-id="bbed1-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="bbed1-113">В синтаксисе объявления модуля верхнего уровня необязательное *полное-пространство имен* — это последовательность вложенных имен пространств имен, содержащих модуль.</span><span class="sxs-lookup"><span data-stu-id="bbed1-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="bbed1-114">Полное имя пространства имен не обязательно должно быть объявлено ранее.</span><span class="sxs-lookup"><span data-stu-id="bbed1-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="bbed1-115">Добавлять отступы в модуль верхнего уровня не требуется.</span><span class="sxs-lookup"><span data-stu-id="bbed1-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="bbed1-116">Необходимо задать отступ для всех объявлений в локальных модулях.</span><span class="sxs-lookup"><span data-stu-id="bbed1-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="bbed1-117">В объявлении локального модуля только объявления, имеющие отступ под этим объявлением модуля, являются частью модуля.</span><span class="sxs-lookup"><span data-stu-id="bbed1-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="bbed1-118">Если файл кода не начинается с объявления модуля верхнего уровня или объявления пространства имен, все содержимое файла, включая все локальные модули, станет частью неявно созданного модуля верхнего уровня, который имеет то же имя, что и файл, без расширения. с первой буквы, преобразованной в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="bbed1-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="bbed1-119">Например, рассмотрим следующий файл.</span><span class="sxs-lookup"><span data-stu-id="bbed1-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="bbed1-120">Этот файл будет скомпилирован так, как если бы он был написан таким образом:</span><span class="sxs-lookup"><span data-stu-id="bbed1-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="bbed1-121">Если в файле имеется несколько модулей, необходимо использовать локальное объявление модуля для каждого модуля.</span><span class="sxs-lookup"><span data-stu-id="bbed1-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="bbed1-122">Если объявлено включающее пространство имен, эти модули являются частью включающего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bbed1-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="bbed1-123">Если включающее пространство имен не объявлено, модули становятся частью неявно созданного модуля верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="bbed1-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="bbed1-124">В следующем примере кода показан файл кода, содержащий несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="bbed1-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="bbed1-125">Компилятор неявно создает модуль верхнего уровня с именем `Multiplemodules`, а `MyModule1` и `MyModule2` вложены в этот модуль верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="bbed1-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="bbed1-126">При наличии нескольких файлов в проекте или в одной компиляции или при построении библиотеки необходимо включить объявление пространства имен или объявление модуля в начало файла.</span><span class="sxs-lookup"><span data-stu-id="bbed1-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="bbed1-127">F# Компилятор явно определяет имя модуля только в том случае, если в проекте или в командной строке компиляции имеется только один файл, и вы создаете приложение.</span><span class="sxs-lookup"><span data-stu-id="bbed1-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="bbed1-128">*Модификатор доступности* может быть одним из следующих: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="bbed1-129">Дополнительные сведения см. в статье [Управление доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="bbed1-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="bbed1-130">Значение по умолчанию — "public" (открытый).</span><span class="sxs-lookup"><span data-stu-id="bbed1-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="bbed1-131">Ссылка на код в модулях</span><span class="sxs-lookup"><span data-stu-id="bbed1-131">Referencing Code in Modules</span></span>

<span data-ttu-id="bbed1-132">При ссылке на функции, типы и значения из другого модуля необходимо либо использовать полное имя, либо открыть модуль.</span><span class="sxs-lookup"><span data-stu-id="bbed1-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="bbed1-133">При использовании полного имени необходимо указать пространства имен, модуль и идентификатор нужного элемента программы.</span><span class="sxs-lookup"><span data-stu-id="bbed1-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="bbed1-134">Каждая часть полного пути разделяются точкой (.), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bbed1-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="bbed1-135">Чтобы упростить код, можно открыть модуль или одно или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="bbed1-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="bbed1-136">Дополнительные сведения об открытии пространств имен и модулей см. [в разделе Объявления импорта: ключевое слово `open`](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="bbed1-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="bbed1-137">В следующем примере кода показан модуль верхнего уровня, содержащий весь код до конца файла.</span><span class="sxs-lookup"><span data-stu-id="bbed1-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="bbed1-138">Чтобы использовать этот код из другого файла в том же проекте, необходимо либо использовать полные имена, либо открыть модуль перед использованием функций, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="bbed1-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="bbed1-139">Вложенные модули</span><span class="sxs-lookup"><span data-stu-id="bbed1-139">Nested Modules</span></span>

<span data-ttu-id="bbed1-140">Модули могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="bbed1-140">Modules can be nested.</span></span> <span data-ttu-id="bbed1-141">Внутренние модули должны быть с отступом до объявлений внешних модулей, чтобы указать, что они являются внутренними модулями, а не новыми модулями.</span><span class="sxs-lookup"><span data-stu-id="bbed1-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="bbed1-142">Например, Сравните следующие два примера.</span><span class="sxs-lookup"><span data-stu-id="bbed1-142">For example, compare the following two examples.</span></span> <span data-ttu-id="bbed1-143">Модуль `Z` является внутренним модулем в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bbed1-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="bbed1-144">Но `Z` модуля — это одноуровневый `Y` модуля в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bbed1-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="bbed1-145">Модуль `Z` также является родственным модулем в следующем коде, так как он не имеет отступов, пока другие объявления в модуле `Y`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="bbed1-146">Наконец, если внешний модуль не имеет объявлений и за ним сразу же поступает объявление другого модуля, объявление нового модуля считается внутренним модулем, но компилятор выдаст предупреждение, если второе определение модуля не имеет отступа дальше, чем началь.</span><span class="sxs-lookup"><span data-stu-id="bbed1-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="bbed1-147">Чтобы устранить это предупреждение, помещает внутренний модуль в отступ.</span><span class="sxs-lookup"><span data-stu-id="bbed1-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="bbed1-148">Если требуется, чтобы весь код в файле настроился в одном внешнем модуле и вы хотели использовать внутренние модули, внешний модуль не требует знака равенства, а объявления, включая любые внутренние объявления модулей, которые будут находиться во внешнем модуле, не должны иметь отступов.</span><span class="sxs-lookup"><span data-stu-id="bbed1-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="bbed1-149">Объявления внутри внутренних объявлений модуля должны иметь отступы.</span><span class="sxs-lookup"><span data-stu-id="bbed1-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="bbed1-150">Этот случай показан в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bbed1-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="bbed1-151">Рекурсивные модули</span><span class="sxs-lookup"><span data-stu-id="bbed1-151">Recursive modules</span></span>

<span data-ttu-id="bbed1-152">F#в 4,1 введено понятие модулей, которые позволяют взаимно рекурсивно выполнять весь автономный код.</span><span class="sxs-lookup"><span data-stu-id="bbed1-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="bbed1-153">Это выполняется с помощью `module rec`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-153">This is done via `module rec`.</span></span>  <span data-ttu-id="bbed1-154">Использование `module rec` может сократить некоторые трудности, не позволяя писать взаимно ссылочный код между типами и модулями.</span><span class="sxs-lookup"><span data-stu-id="bbed1-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="bbed1-155">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="bbed1-155">The following is an example of this:</span></span>

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

<span data-ttu-id="bbed1-156">Обратите внимание, что исключение `DontSqueezeTheBananaException` и класс `Banana` оба ссылаются друг на друга.</span><span class="sxs-lookup"><span data-stu-id="bbed1-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="bbed1-157">Кроме того, модуль `BananaHelpers` и класс `Banana` также ссылаются друг на друга.</span><span class="sxs-lookup"><span data-stu-id="bbed1-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="bbed1-158">Это невозможно, F# если вы удалили ключевое слово `rec` из модуля `RecursiveModule`.</span><span class="sxs-lookup"><span data-stu-id="bbed1-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="bbed1-159">Эта возможность также возможна в [пространствах имен](namespaces.md) с F# 4,1.</span><span class="sxs-lookup"><span data-stu-id="bbed1-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbed1-160">См. также</span><span class="sxs-lookup"><span data-stu-id="bbed1-160">See also</span></span>

- [<span data-ttu-id="bbed1-161">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="bbed1-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bbed1-162">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="bbed1-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="bbed1-163">F#RFC FS-1009 — разрешить взаимно ссылочные типы и модули в более крупных областях внутри файлов</span><span class="sxs-lookup"><span data-stu-id="bbed1-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
