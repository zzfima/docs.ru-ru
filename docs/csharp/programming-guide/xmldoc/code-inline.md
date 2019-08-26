---
title: <c> — руководство по программированию на C#
ms.custom: seodec18
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
ms.openlocfilehash: c881b9ec577fb04381f9e10c7df8f9d0da44cd66
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588182"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="52c85-102">\<c> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="52c85-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="52c85-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52c85-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="52c85-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="52c85-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="52c85-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="52c85-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52c85-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="52c85-106">Remarks</span></span>  
 <span data-ttu-id="52c85-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="52c85-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="52c85-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="52c85-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="52c85-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="52c85-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c85-110">Пример</span><span class="sxs-lookup"><span data-stu-id="52c85-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="52c85-111">См. также</span><span class="sxs-lookup"><span data-stu-id="52c85-111">See also</span></span>

- [<span data-ttu-id="52c85-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="52c85-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="52c85-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="52c85-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
