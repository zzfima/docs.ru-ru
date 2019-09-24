---
title: Идентификаторы Source Line, File и Path
description: Узнайте, как использовать встроенные значения F# идентификатора, которые позволяют получить доступ к номеру строки исходного кода, каталогу и имени файла в коде.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216748"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="a7210-103">Идентификаторы Source Line, File и Path</span><span class="sxs-lookup"><span data-stu-id="a7210-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="a7210-104">Идентификаторы `__LINE__` `__SOURCE_DIRECTORY__` и`__SOURCE_FILE__` являются встроенными значениями, которые позволяют получить доступ к номеру исходной строки, каталогу и имени файла в коде.</span><span class="sxs-lookup"><span data-stu-id="a7210-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7210-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7210-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="a7210-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7210-106">Remarks</span></span>

<span data-ttu-id="a7210-107">Каждое из этих значений имеет тип `string`.</span><span class="sxs-lookup"><span data-stu-id="a7210-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="a7210-108">В следующей таблице перечислены идентификаторы исходной строки, файла и пути, доступные в F#.</span><span class="sxs-lookup"><span data-stu-id="a7210-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="a7210-109">Эти идентификаторы не являются макросами препроцессора; они представляют собой встроенные значения, распознаваемые компилятором.</span><span class="sxs-lookup"><span data-stu-id="a7210-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="a7210-110">Предопределенный идентификатор</span><span class="sxs-lookup"><span data-stu-id="a7210-110">Predefined identifier</span></span>|<span data-ttu-id="a7210-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a7210-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="a7210-112">Вычисляется до текущего номера строки, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a7210-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="a7210-113">Вычисляет текущий полный путь к исходному каталогу, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a7210-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="a7210-114">Вычисляет текущее имя исходного файла без пути, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a7210-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="a7210-115">Дополнительные сведения об директиве `#line` см. в разделе [директивы компилятора](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="a7210-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="a7210-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a7210-116">Example</span></span>

<span data-ttu-id="a7210-117">В следующем примере кода показано использование этих значений.</span><span class="sxs-lookup"><span data-stu-id="a7210-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="a7210-118">Результат</span><span class="sxs-lookup"><span data-stu-id="a7210-118">Output:</span></span>

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="a7210-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a7210-119">See also</span></span>

- [<span data-ttu-id="a7210-120">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="a7210-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="a7210-121">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="a7210-121">F# Language Reference</span></span>](index.md)
