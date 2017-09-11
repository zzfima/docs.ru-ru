---
title: "&lt;typeparam&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
dev_langs:
- CSharp
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8bb1d13976cf2cc9df4f573702168c6abdfff3d5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="41b6b-102">&lt;typeparam&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="41b6b-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="41b6b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41b6b-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41b6b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="41b6b-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="41b6b-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="41b6b-105">The name of the type parameter.</span></span> <span data-ttu-id="41b6b-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="41b6b-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="41b6b-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="41b6b-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41b6b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="41b6b-108">Remarks</span></span>  
 <span data-ttu-id="41b6b-109">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="41b6b-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="41b6b-110">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="41b6b-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="41b6b-111">Дополнительные сведения см. в статье [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="41b6b-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="41b6b-112">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)).</span><span class="sxs-lookup"><span data-stu-id="41b6b-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="41b6b-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="41b6b-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b6b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="41b6b-114">Example</span></span>  
 <span data-ttu-id="41b6b-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41b6b-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b6b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="41b6b-116">See Also</span></span>  
 <span data-ttu-id="41b6b-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="41b6b-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="41b6b-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="41b6b-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="41b6b-119">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="41b6b-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

