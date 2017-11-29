---
title: "&lt;typeparamref&gt; (руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 296761f72d3d306c4f37632d7110e31b62c44734
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="f5ef5-102">&lt;typeparamref&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f5ef5-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f5ef5-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5ef5-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5ef5-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5ef5-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f5ef5-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="f5ef5-105">The name of the type parameter.</span></span> <span data-ttu-id="f5ef5-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="f5ef5-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5ef5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5ef5-107">Remarks</span></span>  
 <span data-ttu-id="f5ef5-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5ef5-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="f5ef5-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="f5ef5-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="f5ef5-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f5ef5-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ef5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f5ef5-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f5ef5-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f5ef5-112">See Also</span></span>  
 [<span data-ttu-id="f5ef5-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f5ef5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f5ef5-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f5ef5-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
