---
title: <param> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789759"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="59369-102">Руководство по программированию на C#. \<param></span><span class="sxs-lookup"><span data-stu-id="59369-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="59369-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59369-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="59369-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="59369-104">Parameters</span></span>

- `name`

  <span data-ttu-id="59369-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="59369-105">The name of a method parameter.</span></span> <span data-ttu-id="59369-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="59369-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="59369-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="59369-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="59369-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="59369-108">Remarks</span></span>

<span data-ttu-id="59369-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="59369-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="59369-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="59369-110">To document multiple parameters, use multiple \<param> tags.</span></span>

<span data-ttu-id="59369-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="59369-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>

<span data-ttu-id="59369-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="59369-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="59369-113">Пример</span><span class="sxs-lookup"><span data-stu-id="59369-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="59369-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59369-114">See also</span></span>

- [<span data-ttu-id="59369-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="59369-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="59369-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="59369-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
