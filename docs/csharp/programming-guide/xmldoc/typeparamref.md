---
title: Руководство по программированию на C#. <typeparamref>
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789663"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="99763-102">Руководство по программированию на C#. \<typeparamref></span><span class="sxs-lookup"><span data-stu-id="99763-102">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="99763-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99763-103">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="99763-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="99763-104">Parameters</span></span>

- `name`

  <span data-ttu-id="99763-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="99763-105">The name of the type parameter.</span></span> <span data-ttu-id="99763-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="99763-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="99763-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="99763-107">Remarks</span></span>

<span data-ttu-id="99763-108">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="99763-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="99763-109">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="99763-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="99763-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="99763-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="99763-111">Пример</span><span class="sxs-lookup"><span data-stu-id="99763-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="99763-112">См. также</span><span class="sxs-lookup"><span data-stu-id="99763-112">See also</span></span>

- [<span data-ttu-id="99763-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="99763-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="99763-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="99763-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
