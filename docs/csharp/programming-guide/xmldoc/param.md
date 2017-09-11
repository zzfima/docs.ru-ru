---
title: "&lt;param&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs:
- CSharp
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
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
ms.openlocfilehash: 1076405d60c85540eeaeba39821bd20bc628030d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="b937c-102">&lt;param&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b937c-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b937c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b937c-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b937c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="b937c-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b937c-105">Имя параметра метода.</span><span class="sxs-lookup"><span data-stu-id="b937c-105">The name of a method parameter.</span></span> <span data-ttu-id="b937c-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="b937c-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="b937c-107">Описание параметра.</span><span class="sxs-lookup"><span data-stu-id="b937c-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b937c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b937c-108">Remarks</span></span>  
 <span data-ttu-id="b937c-109">Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода.</span><span class="sxs-lookup"><span data-stu-id="b937c-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="b937c-110">Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.</span><span class="sxs-lookup"><span data-stu-id="b937c-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="b937c-111">Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.</span><span class="sxs-lookup"><span data-stu-id="b937c-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="b937c-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b937c-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b937c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b937c-113">Example</span></span>  
 <span data-ttu-id="b937c-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b937c-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b937c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b937c-115">See Also</span></span>  
 <span data-ttu-id="b937c-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b937c-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b937c-117">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="b937c-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

