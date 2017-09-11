---
title: "&lt;value&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <value>
dev_langs:
- CSharp
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
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
ms.openlocfilehash: 71c8d5ab2e99291f05ef362960b0eeac969e9de1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="f3a47-102">&lt;value&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f3a47-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f3a47-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3a47-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3a47-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3a47-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="f3a47-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="f3a47-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3a47-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3a47-106">Remarks</span></span>  
 <span data-ttu-id="f3a47-107">Тег \<value> позволяет описывать значение, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="f3a47-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="f3a47-108">Обратите внимание, что при добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="f3a47-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="f3a47-109">После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="f3a47-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="f3a47-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f3a47-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3a47-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f3a47-111">Example</span></span>  
 <span data-ttu-id="f3a47-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f3a47-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a47-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f3a47-113">See Also</span></span>  
 <span data-ttu-id="f3a47-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3a47-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f3a47-115">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f3a47-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

