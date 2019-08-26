---
title: <paramref> — руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e442b6829859ebc4dce6a0f5b6cd6cb777ab1400
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587905"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="81d16-102">\<paramref> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="81d16-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="81d16-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81d16-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="81d16-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="81d16-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="81d16-105">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="81d16-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="81d16-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="81d16-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81d16-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="81d16-107">Remarks</span></span>  
 <span data-ttu-id="81d16-108">Тег \<paramref> позволяет указать, что слово в комментариях к коду, например в блоке \<summary> или \<remarks>, ссылается на параметр.</span><span class="sxs-lookup"><span data-stu-id="81d16-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="81d16-109">В XML-файл такое слово может выделяться особым образом, например курсивом или полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="81d16-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="81d16-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="81d16-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81d16-111">Пример</span><span class="sxs-lookup"><span data-stu-id="81d16-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="81d16-112">См. также</span><span class="sxs-lookup"><span data-stu-id="81d16-112">See also</span></span>

- [<span data-ttu-id="81d16-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="81d16-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="81d16-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="81d16-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
