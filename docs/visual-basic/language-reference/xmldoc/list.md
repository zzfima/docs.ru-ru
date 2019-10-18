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
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524747"
---
# <a name="list-visual-basic"></a><span data-ttu-id="298d0-102">> \<list (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="298d0-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="298d0-103">Определяет список или таблицу.</span><span class="sxs-lookup"><span data-stu-id="298d0-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="298d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="298d0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="298d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="298d0-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="298d0-106">Тип списка.</span><span class="sxs-lookup"><span data-stu-id="298d0-106">The type of the list.</span></span> <span data-ttu-id="298d0-107">Должен быть "маркированным" для маркированного списка, "число" для нумерованного списка или "Таблица" для таблицы из двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="298d0-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="298d0-108">Используется, только если `type` имеет значение "Table".</span><span class="sxs-lookup"><span data-stu-id="298d0-108">Only used when `type` is "table."</span></span> <span data-ttu-id="298d0-109">Термин для определения, который определен в теге description.</span><span class="sxs-lookup"><span data-stu-id="298d0-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="298d0-110">Если `type` имеет значение "маркированный" или "число", `description` является элементом списка, если `type` "Таблица", `description` является определением `term`.</span><span class="sxs-lookup"><span data-stu-id="298d0-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="298d0-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="298d0-111">Remarks</span></span>  
 <span data-ttu-id="298d0-112">Блок `<listheader>` определяет заголовок таблицы или списка определений.</span><span class="sxs-lookup"><span data-stu-id="298d0-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="298d0-113">При определении таблицы необходимо указать в заголовке только запись для `term`.</span><span class="sxs-lookup"><span data-stu-id="298d0-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="298d0-114">Каждый элемент в списке задается блоком `<item>`.</span><span class="sxs-lookup"><span data-stu-id="298d0-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="298d0-115">При создании списка определений необходимо указать и `term`, и `description`.</span><span class="sxs-lookup"><span data-stu-id="298d0-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="298d0-116">Однако для таблицы, маркированного списка или нумерованного списка необходимо указать только запись для `description`.</span><span class="sxs-lookup"><span data-stu-id="298d0-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="298d0-117">Список или таблица может содержать столько `<item>` блоков, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="298d0-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="298d0-118">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="298d0-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="298d0-119">Пример</span><span class="sxs-lookup"><span data-stu-id="298d0-119">Example</span></span>  
 <span data-ttu-id="298d0-120">В этом примере тег `<list>` используется для определения маркированного списка в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="298d0-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="298d0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="298d0-121">See also</span></span>

- [<span data-ttu-id="298d0-122">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="298d0-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
