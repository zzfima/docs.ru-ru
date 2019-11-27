---
title: <list>
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
ms.openlocfilehash: db5c571d2f2c59419c886f6596f4e4dbd30d7baf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352325"
---
# <a name="list-visual-basic"></a><span data-ttu-id="708a6-101">> списка \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="708a6-101">\<list> (Visual Basic)</span></span>
<span data-ttu-id="708a6-102">Определяет список или таблицу.</span><span class="sxs-lookup"><span data-stu-id="708a6-102">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708a6-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="708a6-103">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="708a6-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="708a6-104">Parameters</span></span>  
 `type`  
 <span data-ttu-id="708a6-105">Тип списка.</span><span class="sxs-lookup"><span data-stu-id="708a6-105">The type of the list.</span></span> <span data-ttu-id="708a6-106">Должен быть "маркированным" для маркированного списка, "число" для нумерованного списка или "Таблица" для таблицы из двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="708a6-106">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="708a6-107">Используется, только если `type` имеет значение "Table".</span><span class="sxs-lookup"><span data-stu-id="708a6-107">Only used when `type` is "table."</span></span> <span data-ttu-id="708a6-108">Термин для определения, который определен в теге description.</span><span class="sxs-lookup"><span data-stu-id="708a6-108">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="708a6-109">Если `type` имеет значение "маркированный" или "число", `description` является элементом списка, если `type` "Таблица", `description` является определением `term`.</span><span class="sxs-lookup"><span data-stu-id="708a6-109">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="708a6-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="708a6-110">Remarks</span></span>  
 <span data-ttu-id="708a6-111">Блок `<listheader>` определяет заголовок таблицы или списка определений.</span><span class="sxs-lookup"><span data-stu-id="708a6-111">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="708a6-112">При определении таблицы необходимо указать в заголовке только запись для `term`.</span><span class="sxs-lookup"><span data-stu-id="708a6-112">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="708a6-113">Каждый элемент в списке задается блоком `<item>`.</span><span class="sxs-lookup"><span data-stu-id="708a6-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="708a6-114">При создании списка определений необходимо указать и `term`, и `description`.</span><span class="sxs-lookup"><span data-stu-id="708a6-114">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="708a6-115">Однако для таблицы, маркированного списка или нумерованного списка необходимо указать только запись для `description`.</span><span class="sxs-lookup"><span data-stu-id="708a6-115">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="708a6-116">Список или таблица может содержать столько `<item>` блоков, сколько необходимо.</span><span class="sxs-lookup"><span data-stu-id="708a6-116">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="708a6-117">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="708a6-117">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="708a6-118">Пример</span><span class="sxs-lookup"><span data-stu-id="708a6-118">Example</span></span>  
 <span data-ttu-id="708a6-119">В этом примере тег `<list>` используется для определения маркированного списка в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="708a6-119">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="708a6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="708a6-120">See also</span></span>

- [<span data-ttu-id="708a6-121">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="708a6-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
