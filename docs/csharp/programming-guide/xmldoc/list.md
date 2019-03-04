---
title: <list> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 888f6c823313c137be4b89e82f0c4cd1c50cf771
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977478"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="75360-102">\<list> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="75360-102">\<list> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="75360-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75360-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75360-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="75360-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="75360-105">Термин, который будет определен в `description`.</span><span class="sxs-lookup"><span data-stu-id="75360-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="75360-106">Либо элемент маркированного или нумерованного списка, либо определение `term`.</span><span class="sxs-lookup"><span data-stu-id="75360-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75360-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="75360-107">Remarks</span></span>  
 <span data-ttu-id="75360-108">Блок \<listheader> используется для определения строки заголовка в таблице или списке определений.</span><span class="sxs-lookup"><span data-stu-id="75360-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="75360-109">При определении таблицы необходимо ввести данные для термина в заголовке.</span><span class="sxs-lookup"><span data-stu-id="75360-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="75360-110">Каждый элемент в списке указывается в блоке \<item>.</span><span class="sxs-lookup"><span data-stu-id="75360-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="75360-111">При создании списка определений необходимо указать одновременно `term` и `description`.</span><span class="sxs-lookup"><span data-stu-id="75360-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="75360-112">Тем не менее для таблицы, маркированного или нумерованного списка достаточно ввести только `description`.</span><span class="sxs-lookup"><span data-stu-id="75360-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="75360-113">Число блоков \<item> в списке или таблице не ограничено.</span><span class="sxs-lookup"><span data-stu-id="75360-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="75360-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="75360-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75360-115">Пример</span><span class="sxs-lookup"><span data-stu-id="75360-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]  
  
## <a name="see-also"></a><span data-ttu-id="75360-116">См. также</span><span class="sxs-lookup"><span data-stu-id="75360-116">See also</span></span>

- [<span data-ttu-id="75360-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="75360-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="75360-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="75360-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
