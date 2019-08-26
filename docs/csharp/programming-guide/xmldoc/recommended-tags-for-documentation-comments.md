---
title: Руководство по программированию на C#. Рекомендуемые теги для комментирования документации
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: ac8629dacbb8c1fde1f55468e5d2aeaf78cfe017
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928030"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="f8cb0-102">Рекомендуемые теги для комментариев документации (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f8cb0-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="f8cb0-103">Компилятор C# обрабатывает комментарии документации в коде и форматирует их в виде XML-файла, имя которого задается с помощью параметра командной строки **/doc**.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="f8cb0-104">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="f8cb0-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="f8cb0-105">Теги обрабатываются в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8cb0-106">Комментарии документации не применяются к пространству имен.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="f8cb0-107">Компилятор обрабатывает любые теги, имеющие допустимый формат XML.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="f8cb0-108">С помощью следующих тегов реализуются часто используемые в пользовательской документации возможности.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="f8cb0-109">Теги</span><span class="sxs-lookup"><span data-stu-id="f8cb0-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="f8cb0-110">\<c></span><span class="sxs-lookup"><span data-stu-id="f8cb0-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="f8cb0-111">\<para></span><span class="sxs-lookup"><span data-stu-id="f8cb0-111">\<para></span></span>](./para.md)|<span data-ttu-id="f8cb0-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="f8cb0-113">\<code></span><span class="sxs-lookup"><span data-stu-id="f8cb0-113">\<code></span></span>](./code.md)|<span data-ttu-id="f8cb0-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="f8cb0-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="f8cb0-116">\<example></span><span class="sxs-lookup"><span data-stu-id="f8cb0-116">\<example></span></span>](./example.md)|[<span data-ttu-id="f8cb0-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="f8cb0-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="f8cb0-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="f8cb0-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="f8cb0-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="f8cb0-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="f8cb0-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="f8cb0-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="f8cb0-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="f8cb0-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="f8cb0-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="f8cb0-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="f8cb0-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="f8cb0-125">\<list></span><span class="sxs-lookup"><span data-stu-id="f8cb0-125">\<list></span></span>](./list.md)|[<span data-ttu-id="f8cb0-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="f8cb0-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="f8cb0-127">\<value></span><span class="sxs-lookup"><span data-stu-id="f8cb0-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="f8cb0-128">(\* указывает, что компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="f8cb0-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="f8cb0-129">Чтобы ввести в текст комментария документации угловые скобки, используйте для символов `<` и `>` коды HTML `&lt;` и `&gt;` соответственно.</span><span class="sxs-lookup"><span data-stu-id="f8cb0-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="f8cb0-130">Эти коды используются в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f8cb0-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="f8cb0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f8cb0-131">See also</span></span>

- [<span data-ttu-id="f8cb0-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f8cb0-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f8cb0-133">/doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f8cb0-133">/doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="f8cb0-134">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="f8cb0-134">XML Documentation Comments</span></span>](./index.md)
