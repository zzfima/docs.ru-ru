---
title: "&lt;c&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 21c7830c03b0b93e3597835954ac9e7d2feb49e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="eac97-102">&lt;c&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="eac97-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="eac97-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eac97-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eac97-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="eac97-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="eac97-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="eac97-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eac97-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="eac97-106">Remarks</span></span>  
 <span data-ttu-id="eac97-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="eac97-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="eac97-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="eac97-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="eac97-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="eac97-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eac97-110">Пример</span><span class="sxs-lookup"><span data-stu-id="eac97-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="eac97-111">См. также</span><span class="sxs-lookup"><span data-stu-id="eac97-111">See Also</span></span>  
 [<span data-ttu-id="eac97-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="eac97-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eac97-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="eac97-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
