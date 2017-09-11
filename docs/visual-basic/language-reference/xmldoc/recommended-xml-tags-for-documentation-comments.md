---
title: "Рекомендуемые XML-теги для комментариев документации (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4a6c3128a69e8d666d44882ef3eac9f9a31a51a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="4b7ab-102">Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b7ab-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="4b7ab-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор может обрабатывать комментарии в коде в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="4b7ab-104">Можно использовать дополнительные средства для обработки XML-файла в документации.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="4b7ab-105">Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="4b7ab-106">Для разделяемых типов только одна часть типа может содержать комментарии XML, несмотря на то, что нет ограничений на комментирование его членов.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7ab-107">Комментарии документации не может применяться к пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="4b7ab-108">Это связано с одним пространством имен может охватывать несколько сборок, что не все сборки должны загружаться в то же время.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="4b7ab-109">Компилятор обрабатывает любой тег, допустимый XML-код.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="4b7ab-110">Следующие теги предоставляют часто используемые возможности в пользовательской документации.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="4b7ab-111">\<c настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="4b7ab-112">\<Код настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="4b7ab-113">\<Пример настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="4b7ab-114">[\<исключение настроек](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="4b7ab-115">[\<включить настроек](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="4b7ab-116">\<list></span><span class="sxs-lookup"><span data-stu-id="4b7ab-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="4b7ab-117">\<para настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="4b7ab-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="4b7ab-119">\<paramref настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="4b7ab-120">[\<разрешение настроек](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="4b7ab-121">\<Примечания настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="4b7ab-122">\<Возвращает настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="4b7ab-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="4b7ab-124">[\<seealso настроек](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="4b7ab-125">\<Сводка настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="4b7ab-126">[\<typeparam настроек](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b7ab-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="4b7ab-127">\<значения настроек</span><span class="sxs-lookup"><span data-stu-id="4b7ab-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="4b7ab-128">(<sup>1</sup> компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="4b7ab-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7ab-129">Угловые скобки в текст комментария документации, используйте `<` и `>`.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="4b7ab-130">Например, строка `"<text in angle brackets>"` будет отображаться как `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="4b7ab-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7ab-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4b7ab-131">See Also</span></span>  
 <span data-ttu-id="4b7ab-132">[Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="4b7ab-132">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="4b7ab-133"> [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="4b7ab-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="4b7ab-134"> [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="4b7ab-134"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
