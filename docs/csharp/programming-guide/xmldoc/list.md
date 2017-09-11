---
title: "&lt;list&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
dev_langs:
- CSharp
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
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
ms.openlocfilehash: b9d3dfa60530734a142295c8a8f2c32c4ecd9a47
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="21c63-102">&lt;list&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="21c63-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="21c63-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21c63-103">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="21c63-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="21c63-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="21c63-105">Термин, который будет определен в `description`.</span><span class="sxs-lookup"><span data-stu-id="21c63-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="21c63-106">Либо элемент маркированного или нумерованного списка, либо определение `term`.</span><span class="sxs-lookup"><span data-stu-id="21c63-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21c63-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="21c63-107">Remarks</span></span>  
 <span data-ttu-id="21c63-108">Блок \<listheader> используется для определения строки заголовка в таблице или списке определений.</span><span class="sxs-lookup"><span data-stu-id="21c63-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="21c63-109">При определении таблицы необходимо ввести данные для термина в заголовке.</span><span class="sxs-lookup"><span data-stu-id="21c63-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="21c63-110">Каждый элемент в списке указывается в блоке \<item>.</span><span class="sxs-lookup"><span data-stu-id="21c63-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="21c63-111">При создании списка определений необходимо указать одновременно `term` и `description`.</span><span class="sxs-lookup"><span data-stu-id="21c63-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="21c63-112">Тем не менее для таблицы, маркированного или нумерованного списка достаточно ввести только `description`.</span><span class="sxs-lookup"><span data-stu-id="21c63-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="21c63-113">Число блоков \<item> в списке или таблице не ограничено.</span><span class="sxs-lookup"><span data-stu-id="21c63-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="21c63-114">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="21c63-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21c63-115">Пример</span><span class="sxs-lookup"><span data-stu-id="21c63-115">Example</span></span>  
 <span data-ttu-id="21c63-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="21c63-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c63-117">См. также</span><span class="sxs-lookup"><span data-stu-id="21c63-117">See Also</span></span>  
 <span data-ttu-id="21c63-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="21c63-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="21c63-119">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="21c63-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

