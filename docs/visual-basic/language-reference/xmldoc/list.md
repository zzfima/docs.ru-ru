---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 7d7b85867f4c701322c5e6c31f2d89ab38fad05d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818538"
---
# <a name="list-visual-basic"></a><span data-ttu-id="b56a9-102">\<Список > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b56a9-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="b56a9-103">Определяет список или таблицу.</span><span class="sxs-lookup"><span data-stu-id="b56a9-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b56a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b56a9-104">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
## <a name="parameters"></a><span data-ttu-id="b56a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b56a9-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="b56a9-106">Тип списка.</span><span class="sxs-lookup"><span data-stu-id="b56a9-106">The type of the list.</span></span> <span data-ttu-id="b56a9-107">Должно быть «bullet» для маркированного списка, «number» для нумерованного списка, или «table» для двух столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="b56a9-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="b56a9-108">Используется, только если `type` является «table».</span><span class="sxs-lookup"><span data-stu-id="b56a9-108">Only used when `type` is "table."</span></span> <span data-ttu-id="b56a9-109">Термин, который определен в теге description.</span><span class="sxs-lookup"><span data-stu-id="b56a9-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="b56a9-110">Когда `type` «bullet» или «number», `description` — это элемент в списке при `type` является «table», `description` является определением `term`.</span><span class="sxs-lookup"><span data-stu-id="b56a9-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b56a9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b56a9-111">Remarks</span></span>  
 <span data-ttu-id="b56a9-112">`<listheader>` Блок определяет заголовок таблицы или определение списка.</span><span class="sxs-lookup"><span data-stu-id="b56a9-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="b56a9-113">При определении таблицы необходимо только указать `term` в заголовке.</span><span class="sxs-lookup"><span data-stu-id="b56a9-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="b56a9-114">Каждый элемент в списке указывается с помощью `<item>` блока.</span><span class="sxs-lookup"><span data-stu-id="b56a9-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="b56a9-115">При создании списка определений, должны быть указаны `term` и `description`.</span><span class="sxs-lookup"><span data-stu-id="b56a9-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="b56a9-116">Тем не менее, для таблицы, маркированного или нумерованного списка достаточно указать `description`.</span><span class="sxs-lookup"><span data-stu-id="b56a9-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="b56a9-117">Список или таблица может быть столько `<item>` блокирует при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b56a9-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="b56a9-118">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="b56a9-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b56a9-119">Пример</span><span class="sxs-lookup"><span data-stu-id="b56a9-119">Example</span></span>  
 <span data-ttu-id="b56a9-120">В этом примере используется `<list>` тег для создания маркированного списка в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="b56a9-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b56a9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b56a9-121">See also</span></span>

- [<span data-ttu-id="b56a9-122">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="b56a9-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
