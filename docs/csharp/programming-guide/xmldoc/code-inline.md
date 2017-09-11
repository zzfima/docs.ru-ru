---
title: "&lt;c&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- c
- <c>
dev_langs:
- CSharp
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5a06e25061d4b98ee5e299089455224d39363a63
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="f1d7f-102">&lt;c&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f1d7f-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f1d7f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1d7f-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1d7f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1d7f-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="f1d7f-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d7f-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1d7f-106">Remarks</span></span>  
 <span data-ttu-id="f1d7f-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="f1d7f-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="f1d7f-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="f1d7f-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f1d7f-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1d7f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f1d7f-110">Example</span></span>  
 <span data-ttu-id="f1d7f-111">[!code-cs[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f1d7f-111">[!code-cs[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d7f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d7f-112">See Also</span></span>  
 <span data-ttu-id="f1d7f-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1d7f-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f1d7f-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f1d7f-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

