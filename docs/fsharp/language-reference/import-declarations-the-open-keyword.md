---
title: Объявления импорта. Ключевое слово open
description: Сведения об F# объявлениях импорта и о том, как они указывают модуль или пространство имен, на элементы которых можно ссылаться без использования полного имени.
ms.date: 04/04/2019
ms.openlocfilehash: 816bac551692c3397290f64c6267ee22e4ce90fb
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630572"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="76a9b-103">Объявления импорта. Ключевое слово `open`</span><span class="sxs-lookup"><span data-stu-id="76a9b-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="76a9b-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="76a9b-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="76a9b-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="76a9b-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="76a9b-106">В *объявлении импорта* указан модуль или пространство имен, элементы которого можно ссылаться без использования полного имени.</span><span class="sxs-lookup"><span data-stu-id="76a9b-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="76a9b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76a9b-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="76a9b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="76a9b-108">Remarks</span></span>

<span data-ttu-id="76a9b-109">Создание ссылки на код с помощью полного пространства имен или пути к модулю каждый раз может создать код, который трудно писать, читать и обслуживать.</span><span class="sxs-lookup"><span data-stu-id="76a9b-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="76a9b-110">Вместо этого можно использовать `open` ключевое слово для часто используемых модулей и пространств имен, чтобы при ссылке на член этого модуля или пространства имен можно было использовать краткую форму имени вместо полного имени.</span><span class="sxs-lookup"><span data-stu-id="76a9b-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="76a9b-111">Это ключевое слово похоже на `using` ключевое C#слово `using namespace` в, C++в Visual `Imports` и в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="76a9b-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="76a9b-112">Предоставленный модуль или пространство имен должен находиться в том же проекте или в проекте или сборке, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="76a9b-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="76a9b-113">Если это не так, можно добавить ссылку на проект или использовать `-reference` параметр командной`-`строки `-r`(или его сокращение).</span><span class="sxs-lookup"><span data-stu-id="76a9b-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="76a9b-114">Дополнительные сведения см. в разделе [Параметры компилятора](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="76a9b-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="76a9b-115">Объявление импорта делает имена доступными в коде, который следует за объявлением, вплоть до конца включающего пространства имен, модуля или файла.</span><span class="sxs-lookup"><span data-stu-id="76a9b-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="76a9b-116">При использовании нескольких объявлений импорта они должны отображаться в разных строках.</span><span class="sxs-lookup"><span data-stu-id="76a9b-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="76a9b-117">В следующем коде показано использование `open` ключевого слова для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="76a9b-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="76a9b-118">F# Компилятор не выдает ошибку или предупреждение при возникновении неоднозначности, если одно и то же имя встречается в нескольких открытых модулях или пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="76a9b-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="76a9b-119">При возникновении неоднозначности F# дает предпочтение более последнему открытому модулю или пространству имен.</span><span class="sxs-lookup"><span data-stu-id="76a9b-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="76a9b-120">Например, в следующем коде `empty` это означает, что, несмотря `empty` на то, что `Seq.empty`находится в `List` обоих `Seq` модулях и.</span><span class="sxs-lookup"><span data-stu-id="76a9b-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="76a9b-121">Поэтому будьте внимательны при открытии модулей или пространств имен, таких как `List` или `Seq` , которые содержат элементы с одинаковыми именами. вместо этого рекомендуется использовать полные имена.</span><span class="sxs-lookup"><span data-stu-id="76a9b-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="76a9b-122">Следует избегать ситуаций, в которых код зависит от порядка объявлений импорта.</span><span class="sxs-lookup"><span data-stu-id="76a9b-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="76a9b-123">Пространства имен, открытые по умолчанию</span><span class="sxs-lookup"><span data-stu-id="76a9b-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="76a9b-124">Некоторые пространства имен часто используются в F# коде, который они открывают неявно, без необходимости явного объявления импорта.</span><span class="sxs-lookup"><span data-stu-id="76a9b-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="76a9b-125">В следующей таблице показаны пространства имен, открытые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76a9b-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="76a9b-126">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="76a9b-126">Namespace</span></span>|<span data-ttu-id="76a9b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="76a9b-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="76a9b-128">Содержит базовые F# определения типов для встроенных типов, таких как `int` и `float`.</span><span class="sxs-lookup"><span data-stu-id="76a9b-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="76a9b-129">Содержит базовые арифметические операции, `+` такие `*`как и.</span><span class="sxs-lookup"><span data-stu-id="76a9b-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="76a9b-130">Содержит неизменяемые классы коллекций, `List` такие `Array`как и.</span><span class="sxs-lookup"><span data-stu-id="76a9b-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="76a9b-131">Содержит типы для конструкций элементов управления, таких как отложенная оценка и асинхронные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="76a9b-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="76a9b-132">Содержит функции для форматированного ввода-вывода, `printf` например функции.</span><span class="sxs-lookup"><span data-stu-id="76a9b-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="76a9b-133">Атрибут Автооткрытия</span><span class="sxs-lookup"><span data-stu-id="76a9b-133">AutoOpen Attribute</span></span>

<span data-ttu-id="76a9b-134">`AutoOpen` Атрибут можно применить к сборке, если необходимо автоматически открывать пространство имен или модуль при ссылке на сборку.</span><span class="sxs-lookup"><span data-stu-id="76a9b-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="76a9b-135">Можно также применить `AutoOpen` атрибут к модулю для автоматического открытия этого модуля при открытии родительского модуля или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="76a9b-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="76a9b-136">Дополнительные сведения см. в разделе [класс Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="76a9b-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="76a9b-137">Атрибут Рекуирекуалифиедакцесс</span><span class="sxs-lookup"><span data-stu-id="76a9b-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="76a9b-138">Некоторые модули, записи или типы объединений могут задавать `RequireQualifiedAccess` атрибут.</span><span class="sxs-lookup"><span data-stu-id="76a9b-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="76a9b-139">При ссылке на элементы этих модулей, записей или объединений необходимо использовать полное имя независимо от того, включено ли объявление импорта.</span><span class="sxs-lookup"><span data-stu-id="76a9b-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="76a9b-140">Если этот атрибут используется стратегически для типов, определяющих часто используемые имена, можно избежать конфликтов имен и, таким образом, сделать код более устойчивым к изменениям в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="76a9b-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="76a9b-141">Дополнительные сведения см. в разделе [класс Core. рекуирекуалифиедакцессаттрибуте](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="76a9b-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="76a9b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="76a9b-142">See also</span></span>

- [<span data-ttu-id="76a9b-143">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="76a9b-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="76a9b-144">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="76a9b-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="76a9b-145">Модули</span><span class="sxs-lookup"><span data-stu-id="76a9b-145">Modules</span></span>](modules.md)
