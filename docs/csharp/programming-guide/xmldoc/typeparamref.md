---
title: "&lt;typeparamref&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparamref
dev_langs:
- CSharp
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
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
ms.openlocfilehash: ce2aba7a14047066decf85675233a48a08bfd605
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="6d931-102">&lt;typeparamref&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6d931-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6d931-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d931-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d931-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d931-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6d931-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="6d931-105">The name of the type parameter.</span></span> <span data-ttu-id="6d931-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="6d931-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d931-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d931-107">Remarks</span></span>  
 <span data-ttu-id="6d931-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6d931-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="6d931-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="6d931-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="6d931-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6d931-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d931-111">Пример</span><span class="sxs-lookup"><span data-stu-id="6d931-111">Example</span></span>  
 <span data-ttu-id="6d931-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d931-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d931-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6d931-113">See Also</span></span>  
 <span data-ttu-id="6d931-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d931-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="6d931-115">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="6d931-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

