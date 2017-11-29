---
title: "Объявления импорта: ключевое слово open (F#)"
description: "Дополнительные сведения о объявления импорта F # и как указать модуль или пространство имен, элементы которого можно ссылаться без использования полного имени."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="9d12a-104">Объявления импорта: `open` ключевое слово</span><span class="sxs-lookup"><span data-stu-id="9d12a-104">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="9d12a-105">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="9d12a-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="9d12a-106">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="9d12a-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="9d12a-107">*Объявление импорта* указывает модуль или пространство имен, элементы которого можно ссылаться без использования полного имени.</span><span class="sxs-lookup"><span data-stu-id="9d12a-107">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="9d12a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d12a-108">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="9d12a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d12a-109">Remarks</span></span>
<span data-ttu-id="9d12a-110">Ссылки на код, используя полное имя пространства имен или модуля путь каждый раз можно создать код, который будет сложно запись, чтение и обслуживание.</span><span class="sxs-lookup"><span data-stu-id="9d12a-110">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="9d12a-111">Вместо этого можно использовать `open` ключевое слово для часто используемых модулей и пространств имен, чтобы при ссылке на член этого модуля или пространства имен, можно использовать краткую форму имени вместо полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="9d12a-111">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="9d12a-112">Это ключевое слово аналогично `using` ключевого слова C# `using namespace` в Visual C++ и `Imports` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9d12a-112">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="9d12a-113">Модуль или пространство имен должно быть в одном проекте или в связанном проекте или сборке.</span><span class="sxs-lookup"><span data-stu-id="9d12a-113">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="9d12a-114">Если это не так, можно добавить ссылку на проект, или использовать `-reference` команда`-`строки (или ее сокращением `-r`).</span><span class="sxs-lookup"><span data-stu-id="9d12a-114">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="9d12a-115">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9d12a-115">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="9d12a-116">Объявление импорта доступные имена в коде ниже объявления до конца строки, включающего пространства имен, модуля или файла.</span><span class="sxs-lookup"><span data-stu-id="9d12a-116">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="9d12a-117">При использовании нескольких объявлений импорта, они должны выглядеть на разных строках.</span><span class="sxs-lookup"><span data-stu-id="9d12a-117">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="9d12a-118">В следующем коде показано использование `open` ключевое слово для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="9d12a-118">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="9d12a-119">Компилятор F # не выдает ошибку или предупреждение при возникновении неоднозначности, когда одно имя содержится в нескольких открытых модуль или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9d12a-119">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="9d12a-120">В таких случаях F # отдает предпочтение более недавно открывавшихся модуль или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="9d12a-120">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="9d12a-121">Например, в следующем коде `empty` означает `Seq.empty`, даже если `empty` имеется как `List` и `Seq` модулей.</span><span class="sxs-lookup"><span data-stu-id="9d12a-121">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="9d12a-122">Поэтому будьте внимательны при открытии модули или пространства имен например `List` или `Seq` , содержащие члены, которые имеют одинаковые имена, вместо этого рекомендуется использовать полные имена.</span><span class="sxs-lookup"><span data-stu-id="9d12a-122">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="9d12a-123">Следует избегать любой ситуации, в котором код зависит от порядка объявления импорта.</span><span class="sxs-lookup"><span data-stu-id="9d12a-123">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="9d12a-124">Пространства имен, открываемые по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9d12a-124">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="9d12a-125">Некоторые пространства имен, поэтому часто используются в коде F #, неявно их открытии без необходимости явно указывать объявление импорта.</span><span class="sxs-lookup"><span data-stu-id="9d12a-125">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="9d12a-126">В следующей таблице показаны пространства имен, открываемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d12a-126">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="9d12a-127">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9d12a-127">Namespace</span></span>|<span data-ttu-id="9d12a-128">Описание</span><span class="sxs-lookup"><span data-stu-id="9d12a-128">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="9d12a-129">Содержит определения базовых типов F # для встроенных типов, таких как `int` и `float`.</span><span class="sxs-lookup"><span data-stu-id="9d12a-129">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="9d12a-130">Содержит основные арифметические операции, такие как `+` и `*`.</span><span class="sxs-lookup"><span data-stu-id="9d12a-130">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="9d12a-131">Содержит неизменяемые классы коллекций, такие как `List` и `Array`.</span><span class="sxs-lookup"><span data-stu-id="9d12a-131">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="9d12a-132">Содержит типы для управления конструкций, таких как отложенная оценка и асинхронные рабочие потоки.</span><span class="sxs-lookup"><span data-stu-id="9d12a-132">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="9d12a-133">Содержит функции для форматирования ввода/ВЫВОДА, такие как `printf` функции.</span><span class="sxs-lookup"><span data-stu-id="9d12a-133">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="9d12a-134">AutoOpen-атрибут</span><span class="sxs-lookup"><span data-stu-id="9d12a-134">AutoOpen Attribute</span></span>
<span data-ttu-id="9d12a-135">Можно применить `AutoOpen` атрибут к сборке, чтобы автоматически открыть пространство имен или модуль при ссылке на сборку.</span><span class="sxs-lookup"><span data-stu-id="9d12a-135">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="9d12a-136">Можно также применить `AutoOpen` для модуля, чтобы автоматически открывать его при открытии родительского модуля или пространства имен атрибута.</span><span class="sxs-lookup"><span data-stu-id="9d12a-136">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="9d12a-137">Дополнительные сведения см. в разделе [класс Core.AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="9d12a-137">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="9d12a-138">RequireQualifiedAccess-атрибут</span><span class="sxs-lookup"><span data-stu-id="9d12a-138">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="9d12a-139">Некоторые модули, записи или объединения типов могут указать `RequireQualifiedAccess` атрибута.</span><span class="sxs-lookup"><span data-stu-id="9d12a-139">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="9d12a-140">При ссылке элементы из этих модулей, записи или объединения, необходимо использовать полное имя независимо от того, следует ли включать объявление импорта.</span><span class="sxs-lookup"><span data-stu-id="9d12a-140">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="9d12a-141">Если вы используете этот атрибут стратегически на типы, определяющие часто используемые имена, поможет избежать конфликтов имен и тем самым сделать код более устойчивым к изменениям в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="9d12a-141">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="9d12a-142">Дополнительные сведения см. в разделе [класс Core.RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="9d12a-142">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="9d12a-143">См. также</span><span class="sxs-lookup"><span data-stu-id="9d12a-143">See Also</span></span>
[<span data-ttu-id="9d12a-144"># Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="9d12a-144"># Language Reference</span></span>](index.md)

[<span data-ttu-id="9d12a-145">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="9d12a-145">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="9d12a-146">Модули</span><span class="sxs-lookup"><span data-stu-id="9d12a-146">Modules</span></span>](modules.md)

