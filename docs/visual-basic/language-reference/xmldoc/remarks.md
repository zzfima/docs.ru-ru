---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 90f358aad8e3219b2e3cb3e9b996a24b3138828b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970835"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="efb4c-102">\<"Примечания" > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efb4c-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="efb4c-103">Задает раздел "Примечания" для элемента.</span><span class="sxs-lookup"><span data-stu-id="efb4c-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efb4c-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efb4c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efb4c-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="efb4c-106">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="efb4c-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb4c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="efb4c-107">Remarks</span></span>  
 <span data-ttu-id="efb4c-108">Используйте `<remarks>` тег для добавления сведений о типе, дополняющие информацию, указанный с помощью [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="efb4c-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="efb4c-109">Эта информация отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="efb4c-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="efb4c-110">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="efb4c-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="efb4c-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="efb4c-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efb4c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="efb4c-112">Example</span></span>  
 <span data-ttu-id="efb4c-113">В этом примере используется `<remarks>` тег, чтобы объяснить, что `UpdateRecord` делает метод.</span><span class="sxs-lookup"><span data-stu-id="efb4c-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="efb4c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="efb4c-114">See also</span></span>
- [<span data-ttu-id="efb4c-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="efb4c-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
