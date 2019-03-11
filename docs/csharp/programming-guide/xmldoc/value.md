---
title: <value> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 7f82008d000bf0316b505bfc5d40e9e64b2685a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465197"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="5c8bd-102">\<value> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5c8bd-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5c8bd-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c8bd-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c8bd-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c8bd-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="5c8bd-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="5c8bd-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c8bd-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c8bd-106">Remarks</span></span>  
 <span data-ttu-id="5c8bd-107">Тег \<value> позволяет описывать значение, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="5c8bd-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="5c8bd-108">Обратите внимание, что при добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="5c8bd-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="5c8bd-109">После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="5c8bd-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="5c8bd-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5c8bd-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c8bd-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5c8bd-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="5c8bd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5c8bd-112">See also</span></span>

- [<span data-ttu-id="5c8bd-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5c8bd-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5c8bd-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5c8bd-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
