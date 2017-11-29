---
title: '&lt;para&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2a034974ed94b18da374fbd372063ea4d575440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="824ea-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="824ea-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="824ea-103">Указывает, что содержимое отформатировано как абзац.</span><span class="sxs-lookup"><span data-stu-id="824ea-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="824ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="824ea-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="824ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="824ea-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="824ea-106">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="824ea-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="824ea-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="824ea-107">Remarks</span></span>  
 <span data-ttu-id="824ea-108">`<para>` Тег предназначен для использования внутри тега, например [ \<сводки >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<Примечания >](../../../visual-basic/language-reference/xmldoc/remarks.md), или [ \<возвращает >](../../../visual-basic/language-reference/xmldoc/returns.md), и позволяет добавить структуру к тексту.</span><span class="sxs-lookup"><span data-stu-id="824ea-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="824ea-109">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="824ea-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="824ea-110">Пример</span><span class="sxs-lookup"><span data-stu-id="824ea-110">Example</span></span>  
 <span data-ttu-id="824ea-111">В этом примере используется `<para>` тег для разбиения в разделе "Примечания" `UpdateRecord` метод на два абзаца.</span><span class="sxs-lookup"><span data-stu-id="824ea-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="824ea-112">См. также</span><span class="sxs-lookup"><span data-stu-id="824ea-112">See Also</span></span>  
 [<span data-ttu-id="824ea-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="824ea-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
