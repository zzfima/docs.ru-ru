---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523940"
---
# <a name="c-visual-basic"></a><span data-ttu-id="a92e9-102">> \<c (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a92e9-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="a92e9-103">Указывает, что текст в описании является кодом.</span><span class="sxs-lookup"><span data-stu-id="a92e9-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a92e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a92e9-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a92e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a92e9-105">Parameters</span></span>  
  
|<span data-ttu-id="a92e9-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="a92e9-106">Parameter</span></span>|<span data-ttu-id="a92e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a92e9-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="a92e9-108">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="a92e9-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a92e9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="a92e9-109">Remarks</span></span>  
 <span data-ttu-id="a92e9-110">Тег `<c>` позволяет указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="a92e9-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="a92e9-111">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="a92e9-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="a92e9-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="a92e9-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a92e9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a92e9-113">Example</span></span>  
 <span data-ttu-id="a92e9-114">В этом примере используется тег `<c>` в разделе сводки, чтобы указать, что `Counter` является кодом.</span><span class="sxs-lookup"><span data-stu-id="a92e9-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a92e9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a92e9-115">See also</span></span>

- [<span data-ttu-id="a92e9-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="a92e9-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
