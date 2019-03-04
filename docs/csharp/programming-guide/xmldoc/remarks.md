---
title: <remarks> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 3e6625c55a6f5c29fb55bff2eb87959f3237652e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975861"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="31773-102">\<remarks> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="31773-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="31773-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31773-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31773-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="31773-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="31773-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="31773-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31773-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="31773-106">Remarks</span></span>  
 <span data-ttu-id="31773-107">Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="31773-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="31773-108">Эти сведения отображаются в окне "Обозреватель объектов".</span><span class="sxs-lookup"><span data-stu-id="31773-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="31773-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="31773-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31773-110">Пример</span><span class="sxs-lookup"><span data-stu-id="31773-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="31773-111">См. также</span><span class="sxs-lookup"><span data-stu-id="31773-111">See also</span></span>

- [<span data-ttu-id="31773-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="31773-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="31773-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="31773-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
