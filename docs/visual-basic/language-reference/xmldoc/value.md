---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524602"
---
# <a name="value-visual-basic"></a><span data-ttu-id="b2da3-102">> \<value (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2da3-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="b2da3-103">Задает описание свойства.</span><span class="sxs-lookup"><span data-stu-id="b2da3-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2da3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2da3-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2da3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2da3-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b2da3-106">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="b2da3-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2da3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2da3-107">Remarks</span></span>  
 <span data-ttu-id="b2da3-108">Для описания свойства используйте тег `<value>`.</span><span class="sxs-lookup"><span data-stu-id="b2da3-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="b2da3-109">Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен тег [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="b2da3-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="b2da3-110">Затем следует вручную добавить тег `<value>` для описания значения, которое представляет свойство.</span><span class="sxs-lookup"><span data-stu-id="b2da3-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b2da3-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="b2da3-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2da3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b2da3-112">Example</span></span>  
 <span data-ttu-id="b2da3-113">В этом примере используется тег `<value>` для описания значения, которое содержит свойство `Counter`.</span><span class="sxs-lookup"><span data-stu-id="b2da3-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b2da3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b2da3-114">See also</span></span>

- [<span data-ttu-id="b2da3-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="b2da3-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
