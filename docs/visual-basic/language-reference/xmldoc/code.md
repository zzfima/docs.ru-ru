---
title: "&lt;код&gt; (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="bf5ea-102">&lt;код&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf5ea-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="bf5ea-103">Указывает, что текст является нескольких строк кода.</span><span class="sxs-lookup"><span data-stu-id="bf5ea-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf5ea-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf5ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf5ea-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="bf5ea-106">Текст, который необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="bf5ea-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf5ea-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf5ea-107">Remarks</span></span>  
 <span data-ttu-id="bf5ea-108">Используйте `<code>` тег, чтобы указать несколько строк в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="bf5ea-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="bf5ea-109">С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="bf5ea-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="bf5ea-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="bf5ea-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf5ea-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bf5ea-111">Example</span></span>  
 <span data-ttu-id="bf5ea-112">В этом примере используется \<кода > тег примеры кода, с помощью `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="bf5ea-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bf5ea-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bf5ea-113">See Also</span></span>  
 [<span data-ttu-id="bf5ea-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="bf5ea-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
