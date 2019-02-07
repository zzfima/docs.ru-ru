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
ms.openlocfilehash: 8471681f979fdd030490a5ecc306c4a4b9f624f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276761"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="a61ea-102">\<c> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a61ea-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a61ea-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a61ea-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a61ea-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a61ea-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="a61ea-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="a61ea-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a61ea-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a61ea-106">Remarks</span></span>  
 <span data-ttu-id="a61ea-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="a61ea-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="a61ea-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../csharp/programming-guide/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="a61ea-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="a61ea-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a61ea-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a61ea-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a61ea-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a61ea-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a61ea-111">See also</span></span>

- [<span data-ttu-id="a61ea-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a61ea-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a61ea-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="a61ea-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
