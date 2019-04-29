---
title: Идентификаторы Source Line, File и Path
description: Узнайте, как воспользоваться встроенным F# значений идентификаторов, которые дадут возможность доступа к источнику строка номером, каталогу и имя файла в коде.
ms.date: 05/16/2016
ms.openlocfilehash: 4b145fe1fe20e3d7f868558e33bab26204fb0125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663626"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="a1d3f-103">Идентификаторы Source Line, File и Path</span><span class="sxs-lookup"><span data-stu-id="a1d3f-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="a1d3f-104">Идентификаторы `__LINE__`, `__SOURCE_DIRECTORY__` и `__SOURCE_FILE__` собой встроенные значения, которые позволяют получить доступ к исходной строке номер, каталог и имя файла в коде.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1d3f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1d3f-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="a1d3f-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1d3f-106">Remarks</span></span>

<span data-ttu-id="a1d3f-107">Каждое из этих значений имеет тип `string`.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="a1d3f-108">В следующей таблице перечислены идентификаторы источника line, file и path, доступные в F#.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="a1d3f-109">Эти идентификаторы не макросы препроцессора; они являются встроенные значения, которые распознаются компилятором.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="a1d3f-110">Предопределенный идентификатор</span><span class="sxs-lookup"><span data-stu-id="a1d3f-110">Predefined identifier</span></span>|<span data-ttu-id="a1d3f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a1d3f-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="a1d3f-112">Вычисляет значение текущей строки, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="a1d3f-113">Находит текущий полный путь к исходному каталогу, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="a1d3f-114">Вычисляет текущее имя исходного файла и пути, учитывая `#line` директивы.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|

<span data-ttu-id="a1d3f-115">Дополнительные сведения о `#line` директив, см. в разделе [директивы компилятора](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="a1d3f-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="a1d3f-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a1d3f-116">Example</span></span>

<span data-ttu-id="a1d3f-117">В следующем примере кода показано использование этих значений.</span><span class="sxs-lookup"><span data-stu-id="a1d3f-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="a1d3f-118">Результат</span><span class="sxs-lookup"><span data-stu-id="a1d3f-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="a1d3f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a1d3f-119">See also</span></span>

- [<span data-ttu-id="a1d3f-120">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="a1d3f-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="a1d3f-121">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="a1d3f-121">F# Language Reference</span></span>](index.md)
