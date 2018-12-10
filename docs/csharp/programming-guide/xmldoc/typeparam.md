---
title: '&lt;typeparam&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5db257cc655b7d9112fc4efc917f5d2175fcf665
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143120"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="7e755-102">&lt;typeparam&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7e755-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="7e755-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e755-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e755-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e755-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7e755-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7e755-105">The name of the type parameter.</span></span> <span data-ttu-id="7e755-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="7e755-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="7e755-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7e755-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e755-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e755-108">Remarks</span></span>  
 <span data-ttu-id="7e755-109">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7e755-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="7e755-110">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="7e755-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="7e755-111">Дополнительные сведения см. в статье [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="7e755-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="7e755-112">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)).</span><span class="sxs-lookup"><span data-stu-id="7e755-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="7e755-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7e755-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e755-114">Пример</span><span class="sxs-lookup"><span data-stu-id="7e755-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7e755-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7e755-115">See Also</span></span>

- [<span data-ttu-id="7e755-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7e755-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7e755-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7e755-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7e755-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="7e755-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
