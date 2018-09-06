---
title: '&lt;"Примечания"&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 97fca8758d9c21ac0b8f15bf9d5831750fbabe77
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863037"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="37fd5-102">&lt;"Примечания"&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37fd5-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="37fd5-103">Задает раздел "Примечания" для элемента.</span><span class="sxs-lookup"><span data-stu-id="37fd5-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37fd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37fd5-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37fd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37fd5-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="37fd5-106">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="37fd5-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37fd5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="37fd5-107">Remarks</span></span>  
 <span data-ttu-id="37fd5-108">Используйте `<remarks>` тег для добавления сведений о типе, дополняющие информацию, указанный с помощью [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="37fd5-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="37fd5-109">Эта информация отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="37fd5-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="37fd5-110">Сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="37fd5-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="37fd5-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="37fd5-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37fd5-112">Пример</span><span class="sxs-lookup"><span data-stu-id="37fd5-112">Example</span></span>  
 <span data-ttu-id="37fd5-113">В этом примере используется `<remarks>` тег, чтобы объяснить, что `UpdateRecord` делает метод.</span><span class="sxs-lookup"><span data-stu-id="37fd5-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="37fd5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="37fd5-114">See Also</span></span>  
 [<span data-ttu-id="37fd5-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="37fd5-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
