---
title: Руководство по программированию на C#. Тег &lt;value&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: e3b77af312abcc99945a22abf2b73ebd47556026
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234530"
---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="a0b2f-102">&lt;value&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a0b2f-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a0b2f-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0b2f-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0b2f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0b2f-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="a0b2f-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="a0b2f-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b2f-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0b2f-106">Remarks</span></span>  
 <span data-ttu-id="a0b2f-107">Тег \<value> позволяет описывать значение, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="a0b2f-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="a0b2f-108">Обратите внимание, что при добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="a0b2f-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="a0b2f-109">После этого следует вручную добавить тег \<value> для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="a0b2f-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="a0b2f-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a0b2f-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0b2f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a0b2f-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b2f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a0b2f-112">See Also</span></span>

- [<span data-ttu-id="a0b2f-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a0b2f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a0b2f-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="a0b2f-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
