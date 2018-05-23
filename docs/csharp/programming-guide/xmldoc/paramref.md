---
title: '&lt;paramref&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 0b0d49b90e097e23d3878281f9accda14b057720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="92969-102">&lt;paramref&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="92969-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="92969-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92969-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92969-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="92969-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="92969-105">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="92969-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="92969-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="92969-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92969-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="92969-107">Remarks</span></span>  
 <span data-ttu-id="92969-108">Тег \<paramref> позволяет указать, что слово в комментариях к коду, например в блоке \<summary> или \<remarks>, ссылается на параметр.</span><span class="sxs-lookup"><span data-stu-id="92969-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="92969-109">В XML-файл такое слово может выделяться особым образом, например курсивом или полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="92969-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="92969-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="92969-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92969-111">Пример</span><span class="sxs-lookup"><span data-stu-id="92969-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="92969-112">См. также</span><span class="sxs-lookup"><span data-stu-id="92969-112">See Also</span></span>  
 [<span data-ttu-id="92969-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="92969-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="92969-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="92969-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
