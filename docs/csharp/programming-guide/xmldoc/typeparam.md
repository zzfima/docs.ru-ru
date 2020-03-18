---
title: <typeparam> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793368"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="9689a-102">Руководство по программированию на C#. \<typeparam></span><span class="sxs-lookup"><span data-stu-id="9689a-102">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9689a-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9689a-103">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="9689a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="9689a-104">Parameters</span></span>

- `name`

  <span data-ttu-id="9689a-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="9689a-105">The name of the type parameter.</span></span> <span data-ttu-id="9689a-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="9689a-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="9689a-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="9689a-107">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="9689a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9689a-108">Remarks</span></span>

<span data-ttu-id="9689a-109">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="9689a-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="9689a-110">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="9689a-110">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="9689a-111">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9689a-111">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="9689a-112">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)).</span><span class="sxs-lookup"><span data-stu-id="9689a-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="9689a-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9689a-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9689a-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9689a-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="9689a-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9689a-115">See also</span></span>

- [<span data-ttu-id="9689a-116">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9689a-116">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="9689a-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9689a-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9689a-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="9689a-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
