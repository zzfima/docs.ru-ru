---
title: '&lt;c&gt; (руководство по программированию на C#)'
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
ms.openlocfilehash: 2220c42485674eaa4ba4e3b2dfb03865ad8013cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508151"
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="027e6-102">&lt;c&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="027e6-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="027e6-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="027e6-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="027e6-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="027e6-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="027e6-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="027e6-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="027e6-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="027e6-106">Remarks</span></span>  
 <span data-ttu-id="027e6-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="027e6-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="027e6-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="027e6-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="027e6-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="027e6-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="027e6-110">Пример</span><span class="sxs-lookup"><span data-stu-id="027e6-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="027e6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="027e6-111">See Also</span></span>

- [<span data-ttu-id="027e6-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="027e6-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="027e6-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="027e6-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
