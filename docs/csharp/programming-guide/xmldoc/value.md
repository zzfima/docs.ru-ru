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
ms.openlocfilehash: 1a1a4beb4a3412fe7739a69ecd0fed650b332fb2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263947"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="1cf2b-102">\<value> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1cf2b-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="1cf2b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cf2b-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cf2b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cf2b-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="1cf2b-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="1cf2b-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cf2b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cf2b-106">Remarks</span></span>  
 <span data-ttu-id="1cf2b-107">Тег \<value> позволяет описывать значение, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="1cf2b-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="1cf2b-108">Обратите внимание, что при добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="1cf2b-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="1cf2b-109">После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="1cf2b-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="1cf2b-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1cf2b-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cf2b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="1cf2b-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1cf2b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1cf2b-112">See also</span></span>

- [<span data-ttu-id="1cf2b-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1cf2b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1cf2b-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="1cf2b-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
