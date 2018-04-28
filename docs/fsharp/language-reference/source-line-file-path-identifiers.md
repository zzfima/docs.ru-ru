---
title: Идентификаторы Source Line, File и Path (F#)
description: 'Узнайте, как использовать встроенные значения идентификатора языка F #, которые позволяют получить доступ к номер строки источника, каталог и имя файла в коде.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 18a26f0aa0a0c1f9c0b448ec46eaebd540391324
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="96b97-103">Идентификаторы Source Line, File и Path</span><span class="sxs-lookup"><span data-stu-id="96b97-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="96b97-104">Идентификаторы `__LINE__`, `__SOURCE_DIRECTORY__` и `__SOURCE_FILE__` являются встроенными значениями, которые позволяют получить доступ к исходной строке номер, каталог и имя файла в коде.</span><span class="sxs-lookup"><span data-stu-id="96b97-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="96b97-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96b97-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="96b97-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="96b97-106">Remarks</span></span>
<span data-ttu-id="96b97-107">Каждый из этих значений имеет тип `string`.</span><span class="sxs-lookup"><span data-stu-id="96b97-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="96b97-108">В следующей таблице перечислены строку исходного кода, файлов и путь идентификаторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="96b97-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="96b97-109">Эти идентификаторы не являются макросы препроцессора; они являются встроенными значениями, распознаваемым компилятором.</span><span class="sxs-lookup"><span data-stu-id="96b97-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="96b97-110">Предопределенный идентификатор</span><span class="sxs-lookup"><span data-stu-id="96b97-110">Predefined identifier</span></span>|<span data-ttu-id="96b97-111">Описание</span><span class="sxs-lookup"><span data-stu-id="96b97-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="96b97-112">Вычисляет значение текущей строки, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="96b97-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="96b97-113">Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="96b97-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="96b97-114">Находит текущее имя исходного файла и пути, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="96b97-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="96b97-115">Дополнительные сведения о `#line` директив, см. в разделе [директивы компилятора](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="96b97-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="96b97-116">Пример</span><span class="sxs-lookup"><span data-stu-id="96b97-116">Example</span></span>

<span data-ttu-id="96b97-117">В следующем примере кода показано использование этих значений.</span><span class="sxs-lookup"><span data-stu-id="96b97-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="96b97-118">Результат</span><span class="sxs-lookup"><span data-stu-id="96b97-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="96b97-119">См. также</span><span class="sxs-lookup"><span data-stu-id="96b97-119">See Also</span></span>
[<span data-ttu-id="96b97-120">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="96b97-120">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="96b97-121">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="96b97-121">F# Language Reference</span></span>](index.md)
