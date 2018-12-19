---
title: Руководство по программированию на C#. Тег &lt;remarks&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 75324cbe380b577481b5e8e03f486aa3ef0d5996
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243794"
---
# <a name="ltremarksgt-c-programming-guide"></a><span data-ttu-id="f3bee-102">&lt;remarks&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f3bee-102">&lt;remarks&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f3bee-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3bee-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3bee-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3bee-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="f3bee-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="f3bee-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3bee-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3bee-106">Remarks</span></span>  
 <span data-ttu-id="f3bee-107">Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="f3bee-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="f3bee-108">Эти сведения отображаются в окне "Обозреватель объектов".</span><span class="sxs-lookup"><span data-stu-id="f3bee-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="f3bee-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f3bee-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3bee-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f3bee-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f3bee-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f3bee-111">See Also</span></span>

- [<span data-ttu-id="f3bee-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f3bee-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f3bee-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="f3bee-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
