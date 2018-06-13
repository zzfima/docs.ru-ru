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
ms.openlocfilehash: 623412bae7d2bf58e53dd8290108773d157dd747
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329239"
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="2265c-102">&lt;c&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2265c-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2265c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2265c-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2265c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="2265c-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="2265c-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="2265c-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2265c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="2265c-106">Remarks</span></span>  
 <span data-ttu-id="2265c-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="2265c-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="2265c-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="2265c-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="2265c-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2265c-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2265c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2265c-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2265c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2265c-111">See Also</span></span>  
 [<span data-ttu-id="2265c-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2265c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2265c-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="2265c-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
