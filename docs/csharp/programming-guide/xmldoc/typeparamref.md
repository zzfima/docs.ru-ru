---
title: '&lt;typeparamref&gt;. Руководство по программированию на C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: bbe9bed5a32e463424b98f4066e95374401931e2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243924"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="fe799-102">&lt;typeparamref&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="fe799-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="fe799-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe799-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe799-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe799-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fe799-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="fe799-105">The name of the type parameter.</span></span> <span data-ttu-id="fe799-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="fe799-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe799-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe799-107">Remarks</span></span>  
 <span data-ttu-id="fe799-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="fe799-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="fe799-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="fe799-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="fe799-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="fe799-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe799-111">Пример</span><span class="sxs-lookup"><span data-stu-id="fe799-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fe799-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fe799-112">See Also</span></span>

- [<span data-ttu-id="fe799-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fe799-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="fe799-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="fe799-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
