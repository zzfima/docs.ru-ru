---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524676"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="2e445-102">> \<remarks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e445-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="2e445-103">Задает раздел примечаний для элемента.</span><span class="sxs-lookup"><span data-stu-id="2e445-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e445-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e445-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e445-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e445-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="2e445-106">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="2e445-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e445-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="2e445-107">Remarks</span></span>  
 <span data-ttu-id="2e445-108">Используйте тег `<remarks>`, чтобы добавить сведения о типе, добавив сведения, указанные в [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="2e445-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="2e445-109">Эти сведения отображаются в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="2e445-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="2e445-110">Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="2e445-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="2e445-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="2e445-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e445-112">Пример</span><span class="sxs-lookup"><span data-stu-id="2e445-112">Example</span></span>  
 <span data-ttu-id="2e445-113">В этом примере используется тег `<remarks>` для объяснения того, что делает метод `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="2e445-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2e445-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2e445-114">See also</span></span>

- [<span data-ttu-id="2e445-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="2e445-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
