---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 556c00fa761a1bce5e922a304706c78893550901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599610"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="34282-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34282-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="34282-103">Указывает, что текст в описании кода.</span><span class="sxs-lookup"><span data-stu-id="34282-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34282-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34282-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34282-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34282-105">Parameters</span></span>  
  
|<span data-ttu-id="34282-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="34282-106">Parameter</span></span>|<span data-ttu-id="34282-107">Описание</span><span class="sxs-lookup"><span data-stu-id="34282-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="34282-108">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="34282-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34282-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="34282-109">Remarks</span></span>  
 <span data-ttu-id="34282-110">`<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="34282-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="34282-111">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="34282-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="34282-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="34282-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34282-113">Пример</span><span class="sxs-lookup"><span data-stu-id="34282-113">Example</span></span>  
 <span data-ttu-id="34282-114">В этом примере используется `<c>` тег в сводном разделе, чтобы указать, что `Counter` код.</span><span class="sxs-lookup"><span data-stu-id="34282-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="34282-115">См. также</span><span class="sxs-lookup"><span data-stu-id="34282-115">See Also</span></span>  
 [<span data-ttu-id="34282-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="34282-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
