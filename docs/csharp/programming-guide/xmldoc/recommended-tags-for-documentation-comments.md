---
title: Руководство по программированию на C#. Рекомендуемые теги для комментариев документации
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789725"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="92e9a-102">Руководство по программированию на C#. Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="92e9a-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="92e9a-103">Компилятор C# обрабатывает комментарии документации в коде и форматирует их в виде XML-файла, имя которого задается с помощью параметра командной строки **/doc**.</span><span class="sxs-lookup"><span data-stu-id="92e9a-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="92e9a-104">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="92e9a-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="92e9a-105">Теги обрабатываются в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="92e9a-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="92e9a-106">Комментарии документации не применяются к пространству имен.</span><span class="sxs-lookup"><span data-stu-id="92e9a-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="92e9a-107">Компилятор обрабатывает любые теги, имеющие допустимый формат XML.</span><span class="sxs-lookup"><span data-stu-id="92e9a-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="92e9a-108">С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности.</span><span class="sxs-lookup"><span data-stu-id="92e9a-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="92e9a-109">Tags</span><span class="sxs-lookup"><span data-stu-id="92e9a-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="92e9a-110">\<c></span><span class="sxs-lookup"><span data-stu-id="92e9a-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="92e9a-111">\<para></span><span class="sxs-lookup"><span data-stu-id="92e9a-111">\<para></span></span>](./para.md)|<span data-ttu-id="92e9a-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="92e9a-113">\<value></span><span class="sxs-lookup"><span data-stu-id="92e9a-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="92e9a-114">\<code></span><span class="sxs-lookup"><span data-stu-id="92e9a-114">\<code></span></span>](./code.md)|<span data-ttu-id="92e9a-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="92e9a-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="92e9a-117">\<example></span><span class="sxs-lookup"><span data-stu-id="92e9a-117">\<example></span></span>](./example.md)|[<span data-ttu-id="92e9a-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="92e9a-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="92e9a-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="92e9a-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="92e9a-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="92e9a-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="92e9a-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="92e9a-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="92e9a-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="92e9a-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="92e9a-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="92e9a-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="92e9a-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="92e9a-126">\<list></span><span class="sxs-lookup"><span data-stu-id="92e9a-126">\<list></span></span>](./list.md)|[<span data-ttu-id="92e9a-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="92e9a-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="92e9a-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="92e9a-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="92e9a-129">(\* указывает, что компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="92e9a-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="92e9a-130">Чтобы ввести в текст комментария документации угловые скобки, используйте для символов `<` и `>` коды HTML `&lt;` и `&gt;` соответственно.</span><span class="sxs-lookup"><span data-stu-id="92e9a-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="92e9a-131">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="92e9a-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="92e9a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="92e9a-132">See also</span></span>

- [<span data-ttu-id="92e9a-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="92e9a-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="92e9a-134">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="92e9a-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="92e9a-135">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="92e9a-135">XML documentation comments</span></span>](./index.md)
