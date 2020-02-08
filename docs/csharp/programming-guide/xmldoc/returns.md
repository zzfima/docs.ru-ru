---
title: <returns> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 784d9effa589c962b8a2b982fd199f74309fb4dc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789713"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="5b01b-102">Руководство по программированию на C#. \<returns></span><span class="sxs-lookup"><span data-stu-id="5b01b-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5b01b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b01b-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="5b01b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b01b-104">Parameters</span></span>

- `description`

  <span data-ttu-id="5b01b-105">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="5b01b-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b01b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b01b-106">Remarks</span></span>

<span data-ttu-id="5b01b-107">Тег \<returns> следует использовать в комментариях к объявлению метода для описания возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="5b01b-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="5b01b-108">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5b01b-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="5b01b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5b01b-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="5b01b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5b01b-110">See also</span></span>

- [<span data-ttu-id="5b01b-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5b01b-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5b01b-112">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5b01b-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
