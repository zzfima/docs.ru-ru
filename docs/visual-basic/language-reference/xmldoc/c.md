---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 9be9f9e96fc1b79ea97d54c54352da63b93ef264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838044"
---
# <a name="c-visual-basic"></a><span data-ttu-id="1064b-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1064b-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="1064b-103">Указывает, что текст в описании кода.</span><span class="sxs-lookup"><span data-stu-id="1064b-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1064b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1064b-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1064b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1064b-105">Parameters</span></span>  
  
|<span data-ttu-id="1064b-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="1064b-106">Parameter</span></span>|<span data-ttu-id="1064b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1064b-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="1064b-108">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="1064b-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1064b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1064b-109">Remarks</span></span>  
 <span data-ttu-id="1064b-110">`<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="1064b-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="1064b-111">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="1064b-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="1064b-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="1064b-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1064b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1064b-113">Example</span></span>  
 <span data-ttu-id="1064b-114">В этом примере используется `<c>` тег в разделе сводки, чтобы указать, что `Counter` — это код.</span><span class="sxs-lookup"><span data-stu-id="1064b-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1064b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1064b-115">See also</span></span>

- [<span data-ttu-id="1064b-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="1064b-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
