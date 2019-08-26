---
title: <typeparam> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: ea48cf0cdfc2dc48ad29ab6219449f801739bc8f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587595"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="6597d-102">\<typeparam> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6597d-102">\<typeparam> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6597d-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6597d-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6597d-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="6597d-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6597d-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="6597d-105">The name of the type parameter.</span></span> <span data-ttu-id="6597d-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="6597d-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="6597d-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="6597d-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6597d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6597d-108">Remarks</span></span>  
 <span data-ttu-id="6597d-109">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="6597d-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="6597d-110">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="6597d-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="6597d-111">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6597d-111">For more information, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="6597d-112">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)).</span><span class="sxs-lookup"><span data-stu-id="6597d-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="6597d-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6597d-113">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6597d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="6597d-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="6597d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6597d-115">See also</span></span>

- [<span data-ttu-id="6597d-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6597d-116">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="6597d-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6597d-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6597d-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="6597d-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
