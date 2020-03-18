---
title: Руководство по программированию на C#. Рекомендуемые теги для комментариев документации
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789725"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="d04ba-102">Руководство по программированию на C#. Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="d04ba-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="d04ba-103">Компилятор C# обрабатывает комментарии документации в коде и форматирует их в виде XML-файла, имя которого задается с помощью параметра командной строки **/doc**.</span><span class="sxs-lookup"><span data-stu-id="d04ba-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="d04ba-104">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="d04ba-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="d04ba-105">Теги обрабатываются в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="d04ba-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="d04ba-106">Комментарии документации не применяются к пространству имен.</span><span class="sxs-lookup"><span data-stu-id="d04ba-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="d04ba-107">Компилятор обрабатывает любые теги, имеющие допустимый формат XML.</span><span class="sxs-lookup"><span data-stu-id="d04ba-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="d04ba-108">С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности.</span><span class="sxs-lookup"><span data-stu-id="d04ba-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="d04ba-109">Теги</span><span class="sxs-lookup"><span data-stu-id="d04ba-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="d04ba-110">\<c></span><span class="sxs-lookup"><span data-stu-id="d04ba-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="d04ba-111">\<para></span><span class="sxs-lookup"><span data-stu-id="d04ba-111">\<para></span></span>](./para.md)|<span data-ttu-id="d04ba-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="d04ba-113">\<value></span><span class="sxs-lookup"><span data-stu-id="d04ba-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="d04ba-114">\<code></span><span class="sxs-lookup"><span data-stu-id="d04ba-114">\<code></span></span>](./code.md)|<span data-ttu-id="d04ba-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="d04ba-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="d04ba-117">\<example></span><span class="sxs-lookup"><span data-stu-id="d04ba-117">\<example></span></span>](./example.md)|[<span data-ttu-id="d04ba-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="d04ba-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="d04ba-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="d04ba-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="d04ba-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="d04ba-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="d04ba-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="d04ba-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="d04ba-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="d04ba-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="d04ba-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="d04ba-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="d04ba-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="d04ba-126">\<list></span><span class="sxs-lookup"><span data-stu-id="d04ba-126">\<list></span></span>](./list.md)|[<span data-ttu-id="d04ba-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="d04ba-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="d04ba-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="d04ba-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="d04ba-129">(\* указывает, что компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="d04ba-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="d04ba-130">Чтобы ввести в текст комментария документации угловые скобки, используйте для символов `<` и `>` коды HTML `&lt;` и `&gt;` соответственно.</span><span class="sxs-lookup"><span data-stu-id="d04ba-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="d04ba-131">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d04ba-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="d04ba-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d04ba-132">See also</span></span>

- [<span data-ttu-id="d04ba-133">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d04ba-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="d04ba-134">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="d04ba-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="d04ba-135">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="d04ba-135">XML documentation comments</span></span>](./index.md)
