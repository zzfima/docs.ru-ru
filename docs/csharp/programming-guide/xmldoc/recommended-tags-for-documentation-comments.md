---
title: Рекомендуемые теги для комментариев документации (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 54047746db672efbf626eb2d3fc301b341cc49f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="04da6-102">Рекомендуемые теги для комментариев документации (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="04da6-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="04da6-103">Компилятор C# обрабатывает комментарии документации в коде и форматирует их в виде XML-файла, имя которого задается с помощью параметра командной строки **/doc**.</span><span class="sxs-lookup"><span data-stu-id="04da6-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="04da6-104">Для создания окончательной документации на основе сформированного компилятором файла можно создать пользовательское средство или использовать такое средство, как [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="04da6-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="04da6-105">Теги обрабатываются в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="04da6-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04da6-106">Комментарии документации не применяются к пространству имен.</span><span class="sxs-lookup"><span data-stu-id="04da6-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="04da6-107">Компилятор обрабатывает любые теги, имеющие допустимый формат XML.</span><span class="sxs-lookup"><span data-stu-id="04da6-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="04da6-108">С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности.</span><span class="sxs-lookup"><span data-stu-id="04da6-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="04da6-109">Теги</span><span class="sxs-lookup"><span data-stu-id="04da6-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="04da6-110">\<c></span><span class="sxs-lookup"><span data-stu-id="04da6-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="04da6-111">\<para></span><span class="sxs-lookup"><span data-stu-id="04da6-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="04da6-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="04da6-113">\<code></span><span class="sxs-lookup"><span data-stu-id="04da6-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="04da6-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="04da6-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="04da6-116">\<example></span><span class="sxs-lookup"><span data-stu-id="04da6-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="04da6-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="04da6-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="04da6-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="04da6-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="04da6-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="04da6-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="04da6-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="04da6-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="04da6-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="04da6-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="04da6-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="04da6-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="04da6-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="04da6-125">\<list></span><span class="sxs-lookup"><span data-stu-id="04da6-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="04da6-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="04da6-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="04da6-127">\<value></span><span class="sxs-lookup"><span data-stu-id="04da6-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="04da6-128">(\* указывает, что компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="04da6-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="04da6-129">Чтобы ввести в текст комментария документации угловые скобки, используйте символы `<` и `>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04da6-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04da6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="04da6-130">See Also</span></span>  
 [<span data-ttu-id="04da6-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="04da6-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04da6-132">/doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="04da6-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="04da6-133">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="04da6-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
