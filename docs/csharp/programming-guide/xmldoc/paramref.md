---
title: "&lt;paramref&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- paramref
- <paramref>
dev_langs:
- CSharp
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
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
ms.openlocfilehash: 452701c4f70bf6cbc619064d62de552fa54bba65
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="8eb20-102">&lt;paramref&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8eb20-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8eb20-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eb20-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eb20-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="8eb20-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8eb20-105">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="8eb20-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="8eb20-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="8eb20-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eb20-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8eb20-107">Remarks</span></span>  
 <span data-ttu-id="8eb20-108">Тег \<paramref> позволяет указать, что слово в комментариях к коду, например в блоке \<summary> или \<remarks>, ссылается на параметр.</span><span class="sxs-lookup"><span data-stu-id="8eb20-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="8eb20-109">В XML-файл такое слово может выделяться особым образом, например курсивом или полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="8eb20-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="8eb20-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8eb20-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb20-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8eb20-111">Example</span></span>  
 <span data-ttu-id="8eb20-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8eb20-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb20-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8eb20-113">See Also</span></span>  
 <span data-ttu-id="8eb20-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8eb20-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8eb20-115">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="8eb20-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

