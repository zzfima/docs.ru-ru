---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352249"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="57baf-101">\<Примечания > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57baf-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="57baf-102">Задает раздел примечаний для элемента.</span><span class="sxs-lookup"><span data-stu-id="57baf-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57baf-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57baf-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="57baf-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="57baf-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="57baf-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="57baf-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57baf-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="57baf-106">Remarks</span></span>  
 <span data-ttu-id="57baf-107">Используйте тег `<remarks>`, чтобы добавить сведения о типе, добавив сведения, указанные в [> сводки\<](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="57baf-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="57baf-108">Эти сведения отображаются в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="57baf-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="57baf-109">Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="57baf-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="57baf-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="57baf-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57baf-111">Пример</span><span class="sxs-lookup"><span data-stu-id="57baf-111">Example</span></span>  
 <span data-ttu-id="57baf-112">В этом примере используется тег `<remarks>` для объяснения того, что делает метод `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="57baf-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="57baf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="57baf-113">See also</span></span>

- [<span data-ttu-id="57baf-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="57baf-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
