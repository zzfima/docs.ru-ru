---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041126"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="e1269-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1269-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="e1269-103">Указывает, что текст в описании кода.</span><span class="sxs-lookup"><span data-stu-id="e1269-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1269-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1269-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1269-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1269-105">Parameters</span></span>  
  
|<span data-ttu-id="e1269-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="e1269-106">Parameter</span></span>|<span data-ttu-id="e1269-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e1269-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="e1269-108">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="e1269-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1269-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1269-109">Remarks</span></span>  
 <span data-ttu-id="e1269-110">`<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="e1269-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="e1269-111">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="e1269-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="e1269-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="e1269-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1269-113">Пример</span><span class="sxs-lookup"><span data-stu-id="e1269-113">Example</span></span>  
 <span data-ttu-id="e1269-114">В этом примере используется `<c>` тег в разделе сводки, чтобы указать, что `Counter` — это код.</span><span class="sxs-lookup"><span data-stu-id="e1269-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e1269-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e1269-115">See Also</span></span>  
 [<span data-ttu-id="e1269-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="e1269-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
