---
title: Директивы препроцессора C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "69608596"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="acb78-102">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="acb78-102">C# preprocessor directives</span></span>
<span data-ttu-id="acb78-103">В этом разделе содержатся сведения о следующих директивах препроцессора C#:</span><span class="sxs-lookup"><span data-stu-id="acb78-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="acb78-104">#if</span><span class="sxs-lookup"><span data-stu-id="acb78-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="acb78-105">#else</span><span class="sxs-lookup"><span data-stu-id="acb78-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="acb78-106">#elif</span><span class="sxs-lookup"><span data-stu-id="acb78-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="acb78-107">#endif</span><span class="sxs-lookup"><span data-stu-id="acb78-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="acb78-108">#define</span><span class="sxs-lookup"><span data-stu-id="acb78-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="acb78-109">#undef</span><span class="sxs-lookup"><span data-stu-id="acb78-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="acb78-110">#warning</span><span class="sxs-lookup"><span data-stu-id="acb78-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="acb78-111">#error</span><span class="sxs-lookup"><span data-stu-id="acb78-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="acb78-112">#line</span><span class="sxs-lookup"><span data-stu-id="acb78-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="acb78-113">#region</span><span class="sxs-lookup"><span data-stu-id="acb78-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="acb78-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="acb78-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="acb78-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="acb78-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="acb78-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="acb78-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="acb78-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="acb78-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="acb78-118">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="acb78-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="acb78-119">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="acb78-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="acb78-120">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="acb78-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="acb78-121">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="acb78-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="acb78-122">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="acb78-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="acb78-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="acb78-123">See also</span></span>

- [<span data-ttu-id="acb78-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="acb78-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="acb78-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="acb78-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
