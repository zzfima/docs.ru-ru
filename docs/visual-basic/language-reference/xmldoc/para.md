---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352305"
---
# <a name="para-visual-basic"></a><span data-ttu-id="a570b-101">\<> абзаца (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a570b-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="a570b-102">Указывает, что содержимое форматируется как абзац.</span><span class="sxs-lookup"><span data-stu-id="a570b-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a570b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a570b-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a570b-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a570b-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="a570b-105">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="a570b-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a570b-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a570b-106">Remarks</span></span>  
 <span data-ttu-id="a570b-107">Тег `<para>` предназначен для использования внутри тега, например [\<> сводки](../../../visual-basic/language-reference/xmldoc/summary.md), [\<примечания >](../../../visual-basic/language-reference/xmldoc/remarks.md)или [\<возвращает >](../../../visual-basic/language-reference/xmldoc/returns.md)и позволяет добавлять в текст структуру.</span><span class="sxs-lookup"><span data-stu-id="a570b-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="a570b-108">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="a570b-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a570b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a570b-109">Example</span></span>  
 <span data-ttu-id="a570b-110">В этом примере используется тег `<para>` для разбиения раздела примечаний для метода `UpdateRecord` на два абзаца.</span><span class="sxs-lookup"><span data-stu-id="a570b-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a570b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a570b-111">See also</span></span>

- [<span data-ttu-id="a570b-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="a570b-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
