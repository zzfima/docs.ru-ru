---
title: Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 7830db136e9b900458496b36df5bc37f76661129
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523976"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="b0b80-102">Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0b80-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="b0b80-103">Компилятор Visual Basic может обрабатывать комментарии документации в коде в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="b0b80-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="b0b80-104">Для обработки XML-файла в документации можно использовать дополнительные средства.</span><span class="sxs-lookup"><span data-stu-id="b0b80-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="b0b80-105">Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="b0b80-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="b0b80-106">Для разделяемых типов только одна часть типа может содержать комментарии XML, хотя не существует ограничений на комментирование его элементов.</span><span class="sxs-lookup"><span data-stu-id="b0b80-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0b80-107">Комментарии к документации нельзя применять к пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="b0b80-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="b0b80-108">Причина состоит в том, что одно пространство имен может охватывать несколько сборок, и не все сборки должны быть загружены одновременно.</span><span class="sxs-lookup"><span data-stu-id="b0b80-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="b0b80-109">Компилятор обрабатывает любой тег, который является допустимым XML.</span><span class="sxs-lookup"><span data-stu-id="b0b80-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="b0b80-110">Следующие теги предоставляют часто используемые функции в пользовательской документации.</span><span class="sxs-lookup"><span data-stu-id="b0b80-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="b0b80-111">\<c></span><span class="sxs-lookup"><span data-stu-id="b0b80-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="b0b80-112">\<code></span><span class="sxs-lookup"><span data-stu-id="b0b80-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="b0b80-113">\<example></span><span class="sxs-lookup"><span data-stu-id="b0b80-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="b0b80-114">[\<exception >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="b0b80-115">[\<include >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="b0b80-116">\<list></span><span class="sxs-lookup"><span data-stu-id="b0b80-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="b0b80-117">\<para></span><span class="sxs-lookup"><span data-stu-id="b0b80-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="b0b80-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="b0b80-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="b0b80-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="b0b80-120">[\<permission >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="b0b80-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="b0b80-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="b0b80-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="b0b80-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="b0b80-123">[\<see >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="b0b80-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="b0b80-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="b0b80-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="b0b80-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0b80-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="b0b80-127">\<value></span><span class="sxs-lookup"><span data-stu-id="b0b80-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="b0b80-128">(<sup>1</sup> компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="b0b80-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0b80-129">Если необходимо, чтобы угловые скобки отображались в тексте комментария к документации, используйте `&lt;` и `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="b0b80-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="b0b80-130">Например, строка `"&lt;text in angle brackets&gt;"` будет выглядеть как `<text in angle brackets>`.</span><span class="sxs-lookup"><span data-stu-id="b0b80-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b80-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b0b80-131">See also</span></span>

- [<span data-ttu-id="b0b80-132">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="b0b80-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="b0b80-133">-doc</span><span class="sxs-lookup"><span data-stu-id="b0b80-133">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="b0b80-134">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="b0b80-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
