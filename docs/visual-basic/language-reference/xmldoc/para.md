---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524738"
---
# <a name="para-visual-basic"></a><span data-ttu-id="a2ebf-102">> \<para (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2ebf-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="a2ebf-103">Указывает, что содержимое форматируется как абзац.</span><span class="sxs-lookup"><span data-stu-id="a2ebf-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ebf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2ebf-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2ebf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2ebf-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="a2ebf-106">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="a2ebf-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ebf-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a2ebf-107">Remarks</span></span>  
 <span data-ttu-id="a2ebf-108">Тег `<para>` предназначен для использования внутри тега, например [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md)или [\<returns >](../../../visual-basic/language-reference/xmldoc/returns.md), и позволяет добавить в текст структуру.</span><span class="sxs-lookup"><span data-stu-id="a2ebf-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="a2ebf-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="a2ebf-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ebf-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a2ebf-110">Example</span></span>  
 <span data-ttu-id="a2ebf-111">В этом примере используется тег `<para>` для разбиения раздела примечаний для метода `UpdateRecord` на два абзаца.</span><span class="sxs-lookup"><span data-stu-id="a2ebf-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a2ebf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a2ebf-112">See also</span></span>

- [<span data-ttu-id="a2ebf-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="a2ebf-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
