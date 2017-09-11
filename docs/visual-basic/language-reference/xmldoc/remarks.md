---
title: "&lt;Примечания&gt; (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c1b2c48dc3247935f703ff4107f29829c494a305
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="e12a5-102">&lt;Примечания&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e12a5-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="e12a5-103">Задает раздел примечаний для члена.</span><span class="sxs-lookup"><span data-stu-id="e12a5-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e12a5-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e12a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e12a5-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="e12a5-106">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="e12a5-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e12a5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e12a5-107">Remarks</span></span>  
 <span data-ttu-id="e12a5-108">Используйте `<remarks>` тег для добавления сведений о типе, дополняющих сведения, указанные с [ \<Сводка настроек](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="e12a5-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="e12a5-109">Эта информация отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="e12a5-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="e12a5-110">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="e12a5-110">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="e12a5-111">Скомпилируйте с [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) чтобы обработать комментарии документации в файл.</span><span class="sxs-lookup"><span data-stu-id="e12a5-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e12a5-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e12a5-112">Example</span></span>  
 <span data-ttu-id="e12a5-113">В этом примере используется `<remarks>` тег, чтобы объяснить, что `UpdateRecord` метода.</span><span class="sxs-lookup"><span data-stu-id="e12a5-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 <span data-ttu-id="e12a5-114">[!code-vb[VbVbcnXmlDocComments №&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e12a5-114">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12a5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e12a5-115">See Also</span></span>  
 [<span data-ttu-id="e12a5-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="e12a5-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
