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
ms.openlocfilehash: 9454ef8cc4b72d1d6bdcac26faf76eb17080328c
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523533"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="9c29a-102">\<c> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9c29a-102">\<c> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9c29a-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c29a-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c29a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c29a-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="9c29a-105">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="9c29a-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c29a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c29a-106">Remarks</span></span>  
 <span data-ttu-id="9c29a-107">С помощью тега \<c> можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="9c29a-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="9c29a-108">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="9c29a-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="9c29a-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9c29a-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c29a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9c29a-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9c29a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9c29a-111">See also</span></span>

- [<span data-ttu-id="9c29a-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9c29a-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9c29a-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="9c29a-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
