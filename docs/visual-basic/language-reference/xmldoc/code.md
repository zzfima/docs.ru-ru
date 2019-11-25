---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354327"
---
# <a name="code-visual-basic"></a><span data-ttu-id="59be0-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59be0-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="59be0-102">Indicates that the text is multiple lines of code.</span><span class="sxs-lookup"><span data-stu-id="59be0-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59be0-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59be0-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="59be0-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="59be0-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="59be0-105">The text to mark as code.</span><span class="sxs-lookup"><span data-stu-id="59be0-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59be0-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="59be0-106">Remarks</span></span>  
 <span data-ttu-id="59be0-107">Use the `<code>` tag to indicate multiple lines as code.</span><span class="sxs-lookup"><span data-stu-id="59be0-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="59be0-108">С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="59be0-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="59be0-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="59be0-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59be0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="59be0-110">Example</span></span>  
 <span data-ttu-id="59be0-111">This example uses the \<code> tag to include example code for using the `ID` field.</span><span class="sxs-lookup"><span data-stu-id="59be0-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="59be0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="59be0-112">See also</span></span>

- [<span data-ttu-id="59be0-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="59be0-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
