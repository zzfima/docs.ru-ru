---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 16d10b2f955a4d9a02075ee4cc40dfa2b18c3541
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814514"
---
# <a name="para-visual-basic"></a><span data-ttu-id="db64d-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db64d-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="db64d-103">Указывает, что содержимое отформатировано как абзац.</span><span class="sxs-lookup"><span data-stu-id="db64d-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db64d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db64d-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="db64d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="db64d-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="db64d-106">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="db64d-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db64d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="db64d-107">Remarks</span></span>  
 <span data-ttu-id="db64d-108">`<para>` Тега используется внутри тега, такие как [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<"Примечания" >](../../../visual-basic/language-reference/xmldoc/remarks.md), или [ \<возвращает >](../../../visual-basic/language-reference/xmldoc/returns.md), и позволяет добавить структуру к тексту.</span><span class="sxs-lookup"><span data-stu-id="db64d-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="db64d-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="db64d-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db64d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="db64d-110">Example</span></span>  
 <span data-ttu-id="db64d-111">В этом примере используется `<para>` тег для разбиения в разделе "Примечания" `UpdateRecord` метод на два абзаца.</span><span class="sxs-lookup"><span data-stu-id="db64d-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="db64d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="db64d-112">See also</span></span>

- [<span data-ttu-id="db64d-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="db64d-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
