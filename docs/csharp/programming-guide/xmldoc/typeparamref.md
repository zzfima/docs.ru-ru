---
title: <typeparamref> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a9b0b9dec09e891105336b3cf0088ed279386d13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471932"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="a5bfc-102">\<typeparamref> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a5bfc-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a5bfc-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5bfc-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5bfc-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5bfc-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a5bfc-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-105">The name of the type parameter.</span></span> <span data-ttu-id="a5bfc-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="a5bfc-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5bfc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5bfc-107">Remarks</span></span>  
 <span data-ttu-id="a5bfc-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5bfc-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="a5bfc-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="a5bfc-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="a5bfc-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a5bfc-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5bfc-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a5bfc-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="a5bfc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a5bfc-112">See also</span></span>

- [<span data-ttu-id="a5bfc-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a5bfc-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a5bfc-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="a5bfc-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
