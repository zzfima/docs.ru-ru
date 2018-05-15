---
title: '&lt;Примечания&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 6e4e280760b9238fdc403ac5fe586743334e4c69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="36410-102">&lt;Примечания&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36410-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="36410-103">Задает раздел примечаний для члена.</span><span class="sxs-lookup"><span data-stu-id="36410-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36410-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36410-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36410-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36410-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="36410-106">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="36410-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36410-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="36410-107">Remarks</span></span>  
 <span data-ttu-id="36410-108">Используйте `<remarks>` тег, чтобы добавить сведения о типе, дополняющих сведения, указанный с [ \<сводки >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="36410-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="36410-109">Эта информация отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="36410-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="36410-110">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="36410-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="36410-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="36410-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36410-112">Пример</span><span class="sxs-lookup"><span data-stu-id="36410-112">Example</span></span>  
 <span data-ttu-id="36410-113">В этом примере используется `<remarks>` тег объясняется, что такое `UpdateRecord` метода.</span><span class="sxs-lookup"><span data-stu-id="36410-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="36410-114">См. также</span><span class="sxs-lookup"><span data-stu-id="36410-114">See Also</span></span>  
 [<span data-ttu-id="36410-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="36410-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
