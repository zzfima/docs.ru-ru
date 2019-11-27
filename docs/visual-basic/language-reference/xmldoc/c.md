---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348515"
---
# <a name="c-visual-basic"></a><span data-ttu-id="6eccb-101">> \<c (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6eccb-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="6eccb-102">Указывает, что текст в описании является кодом.</span><span class="sxs-lookup"><span data-stu-id="6eccb-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eccb-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6eccb-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eccb-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="6eccb-104">Parameters</span></span>  
  
|<span data-ttu-id="6eccb-105">Параметр</span><span class="sxs-lookup"><span data-stu-id="6eccb-105">Parameter</span></span>|<span data-ttu-id="6eccb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6eccb-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="6eccb-107">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="6eccb-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eccb-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6eccb-108">Remarks</span></span>  
 <span data-ttu-id="6eccb-109">Тег `<c>` позволяет указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="6eccb-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="6eccb-110">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="6eccb-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="6eccb-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="6eccb-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eccb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6eccb-112">Example</span></span>  
 <span data-ttu-id="6eccb-113">В этом примере используется тег `<c>` в разделе сводки, чтобы указать, что `Counter` является кодом.</span><span class="sxs-lookup"><span data-stu-id="6eccb-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6eccb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6eccb-114">See also</span></span>

- [<span data-ttu-id="6eccb-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="6eccb-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
