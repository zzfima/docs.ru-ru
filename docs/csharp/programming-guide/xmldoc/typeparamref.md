---
title: <typeparamref> — руководство по программированию на C#
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 3e96d55d7cf60b2a9085cf065ef3b8193b173c5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711679"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="6df5e-102">\<typeparamref> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6df5e-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6df5e-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6df5e-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6df5e-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="6df5e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6df5e-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="6df5e-105">The name of the type parameter.</span></span> <span data-ttu-id="6df5e-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="6df5e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6df5e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6df5e-107">Remarks</span></span>  
 <span data-ttu-id="6df5e-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6df5e-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="6df5e-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="6df5e-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="6df5e-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6df5e-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6df5e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="6df5e-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="6df5e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6df5e-112">See also</span></span>

- [<span data-ttu-id="6df5e-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6df5e-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6df5e-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="6df5e-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
