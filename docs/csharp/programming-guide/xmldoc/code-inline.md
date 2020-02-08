---
title: Руководство по программированию на C#. <c>
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793455"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="af2b5-102">Руководство по программированию на C#. \<c></span><span class="sxs-lookup"><span data-stu-id="af2b5-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="af2b5-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af2b5-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="af2b5-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="af2b5-104">Parameters</span></span>

- `text`

  <span data-ttu-id="af2b5-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="af2b5-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af2b5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="af2b5-106">Remarks</span></span>

<span data-ttu-id="af2b5-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="af2b5-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="af2b5-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="af2b5-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="af2b5-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="af2b5-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="af2b5-110">Пример</span><span class="sxs-lookup"><span data-stu-id="af2b5-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="af2b5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="af2b5-111">See also</span></span>

- [<span data-ttu-id="af2b5-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="af2b5-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="af2b5-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="af2b5-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
