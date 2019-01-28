---
title: Руководство по программированию на C#. Тег &lt;c&gt;
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
ms.openlocfilehash: b789b95c5e23534fb36613ac9203f146b265a98d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640991"
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="3cb8b-102">&lt;c&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3cb8b-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3cb8b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cb8b-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cb8b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cb8b-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="3cb8b-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="3cb8b-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cb8b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cb8b-106">Remarks</span></span>  
 <span data-ttu-id="3cb8b-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="3cb8b-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="3cb8b-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="3cb8b-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="3cb8b-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3cb8b-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb8b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3cb8b-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3cb8b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3cb8b-111">See also</span></span>

- [<span data-ttu-id="3cb8b-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3cb8b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3cb8b-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="3cb8b-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
