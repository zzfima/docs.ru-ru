---
title: '&lt;remarks&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: bb0d2f2cd62fd5d4a83d7e66d3b0fea340a914a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330571"
---
# <a name="ltremarksgt-c-programming-guide"></a><span data-ttu-id="5a31c-102">&lt;remarks&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5a31c-102">&lt;remarks&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5a31c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a31c-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a31c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a31c-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="5a31c-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="5a31c-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a31c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a31c-106">Remarks</span></span>  
 <span data-ttu-id="5a31c-107">Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="5a31c-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="5a31c-108">Эти сведения отображаются в окне "Обозреватель объектов".</span><span class="sxs-lookup"><span data-stu-id="5a31c-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="5a31c-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5a31c-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a31c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5a31c-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5a31c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5a31c-111">See Also</span></span>  
 [<span data-ttu-id="5a31c-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5a31c-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5a31c-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5a31c-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
