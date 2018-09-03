---
title: '&lt;код&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: e66aebe35dd8f6443fefe3b07842b37270159e6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475989"
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="ea85f-102">&lt;код&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea85f-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="ea85f-103">Указывает, что текст является несколько строк кода.</span><span class="sxs-lookup"><span data-stu-id="ea85f-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea85f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea85f-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea85f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea85f-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="ea85f-106">Текст, который необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="ea85f-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea85f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea85f-107">Remarks</span></span>  
 <span data-ttu-id="ea85f-108">Используйте `<code>` тег, чтобы указать несколько строк как код.</span><span class="sxs-lookup"><span data-stu-id="ea85f-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="ea85f-109">С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="ea85f-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="ea85f-110">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="ea85f-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea85f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ea85f-111">Example</span></span>  
 <span data-ttu-id="ea85f-112">В этом примере используется \<кода > тег пример кода для использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="ea85f-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ea85f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ea85f-113">See Also</span></span>  
 [<span data-ttu-id="ea85f-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="ea85f-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
