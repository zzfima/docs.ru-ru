---
title: "Идентификаторы Source Line, File и Path (F#)"
description: "Узнайте, как использовать встроенные значения идентификатора языка F #, которые позволяют получить доступ к номер строки источника, каталог и имя файла в коде."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="fb85e-104">Идентификаторы Source Line, File и Path</span><span class="sxs-lookup"><span data-stu-id="fb85e-104">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="fb85e-105">Идентификаторы `__LINE__`, `__SOURCE_DIRECTORY__` и `__SOURCE_FILE__` являются встроенными значениями, которые позволяют получить доступ к исходной строке номер, каталог и имя файла в коде.</span><span class="sxs-lookup"><span data-stu-id="fb85e-105">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="fb85e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb85e-106">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="fb85e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb85e-107">Remarks</span></span>
<span data-ttu-id="fb85e-108">Каждый из этих значений имеет тип `string`.</span><span class="sxs-lookup"><span data-stu-id="fb85e-108">Each of these values has type `string`.</span></span>

<span data-ttu-id="fb85e-109">В следующей таблице перечислены строку исходного кода, файлов и путь идентификаторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="fb85e-109">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="fb85e-110">Эти идентификаторы не являются макросы препроцессора; они являются встроенными значениями, распознаваемым компилятором.</span><span class="sxs-lookup"><span data-stu-id="fb85e-110">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="fb85e-111">Предопределенный идентификатор</span><span class="sxs-lookup"><span data-stu-id="fb85e-111">Predefined identifier</span></span>|<span data-ttu-id="fb85e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fb85e-112">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="fb85e-113">Вычисляет значение текущей строки, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="fb85e-113">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="fb85e-114">Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="fb85e-114">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="fb85e-115">Находит текущее имя исходного файла и пути, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="fb85e-115">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="fb85e-116">Дополнительные сведения о `#line` директив, см. в разделе [директивы компилятора](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="fb85e-116">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="fb85e-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fb85e-117">Example</span></span>

<span data-ttu-id="fb85e-118">В следующем примере кода показано использование этих значений.</span><span class="sxs-lookup"><span data-stu-id="fb85e-118">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="fb85e-119">Результат</span><span class="sxs-lookup"><span data-stu-id="fb85e-119">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="fb85e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fb85e-120">See Also</span></span>
[<span data-ttu-id="fb85e-121">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="fb85e-121">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="fb85e-122">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="fb85e-122">F# Language Reference</span></span>](index.md)
