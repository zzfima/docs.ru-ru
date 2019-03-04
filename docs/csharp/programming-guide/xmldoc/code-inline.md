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
ms.openlocfilehash: e56df10eabc6a2d38bd049951b01c16808222255
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202305"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="0d218-102">\<c> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0d218-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="0d218-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d218-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d218-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d218-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="0d218-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="0d218-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d218-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d218-106">Remarks</span></span>  
 <span data-ttu-id="0d218-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="0d218-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="0d218-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="0d218-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="0d218-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0d218-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d218-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0d218-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0d218-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0d218-111">See also</span></span>

- [<span data-ttu-id="0d218-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d218-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0d218-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="0d218-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
