---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e57cae8fd4b93fee59992d717135ad7d3d78be5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="7b9ed-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b9ed-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="7b9ed-103">Указывает, что текст в описании кода.</span><span class="sxs-lookup"><span data-stu-id="7b9ed-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b9ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b9ed-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b9ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b9ed-105">Parameters</span></span>  
  
|<span data-ttu-id="7b9ed-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="7b9ed-106">Parameter</span></span>|<span data-ttu-id="7b9ed-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7b9ed-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="7b9ed-108">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="7b9ed-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b9ed-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b9ed-109">Remarks</span></span>  
 <span data-ttu-id="7b9ed-110">`<c>` Тег дает возможность указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="7b9ed-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="7b9ed-111">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="7b9ed-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="7b9ed-112">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="7b9ed-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b9ed-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7b9ed-113">Example</span></span>  
 <span data-ttu-id="7b9ed-114">В этом примере используется `<c>` тег в сводном разделе, чтобы указать, что `Counter` код.</span><span class="sxs-lookup"><span data-stu-id="7b9ed-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7b9ed-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7b9ed-115">See Also</span></span>  
 [<span data-ttu-id="7b9ed-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="7b9ed-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
