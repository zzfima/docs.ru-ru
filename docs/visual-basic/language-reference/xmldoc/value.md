---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821418"
---
# <a name="value-visual-basic"></a><span data-ttu-id="b3ccf-102">\<Значение > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3ccf-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="b3ccf-103">Указывает описание свойства.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ccf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3ccf-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3ccf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3ccf-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b3ccf-106">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3ccf-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3ccf-107">Remarks</span></span>  
 <span data-ttu-id="b3ccf-108">Используйте `<value>` тегов для описания свойства.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="b3ccf-109">Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio добавит [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) тег для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="b3ccf-110">Затем следует вручную добавить `<value>` тегов для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b3ccf-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="b3ccf-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3ccf-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b3ccf-112">Example</span></span>  
 <span data-ttu-id="b3ccf-113">В этом примере используется `<value>` тегов для описания какое значение `Counter` содержится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="b3ccf-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b3ccf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b3ccf-114">See also</span></span>

- [<span data-ttu-id="b3ccf-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="b3ccf-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
