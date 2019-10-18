---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524627"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="d098d-102">> \<summary (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d098d-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="d098d-103">Указывает сводку элемента.</span><span class="sxs-lookup"><span data-stu-id="d098d-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d098d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d098d-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d098d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d098d-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d098d-106">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="d098d-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d098d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="d098d-107">Remarks</span></span>  
 <span data-ttu-id="d098d-108">Используйте тег `<summary>` для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="d098d-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="d098d-109">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md).</span><span class="sxs-lookup"><span data-stu-id="d098d-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="d098d-110">Текст для тега `<summary>` является единственным источником сведений о типе в IntelliSense и также отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="d098d-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="d098d-111">Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="d098d-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="d098d-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d098d-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d098d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d098d-113">Example</span></span>  
 <span data-ttu-id="d098d-114">В этом примере используется тег `<summary>` для описания метода `ResetCounter` и свойства `Counter`.</span><span class="sxs-lookup"><span data-stu-id="d098d-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d098d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d098d-115">See also</span></span>

- [<span data-ttu-id="d098d-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d098d-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
