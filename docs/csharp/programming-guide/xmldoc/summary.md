---
title: <summary> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 1ae3c17bef69a52b4d5852e09284929dc328bf8a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789675"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="658a3-102">Руководство по программированию на C#. \<summary></span><span class="sxs-lookup"><span data-stu-id="658a3-102">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="658a3-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="658a3-103">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="658a3-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="658a3-104">Parameters</span></span>

- `description`

  <span data-ttu-id="658a3-105">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="658a3-105">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="658a3-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="658a3-106">Remarks</span></span>

<span data-ttu-id="658a3-107">Тег \<summary> следует использовать для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="658a3-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="658a3-108">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](./remarks.md).</span><span class="sxs-lookup"><span data-stu-id="658a3-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="658a3-109">Чтобы включить средства документации, такие как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="658a3-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="658a3-110">Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="658a3-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="658a3-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="658a3-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="658a3-112">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="658a3-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="658a3-113">Пример</span><span class="sxs-lookup"><span data-stu-id="658a3-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="658a3-114">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="658a3-114">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            <seealso cref="M:TestClass.Main"/>
            </summary>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="658a3-115">Пример</span><span class="sxs-lookup"><span data-stu-id="658a3-115">Example</span></span>

<span data-ttu-id="658a3-116">В следующем примере показано, как создать ссылку `cref` на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="658a3-116">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="658a3-117">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="658a3-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="658a3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="658a3-118">See also</span></span>

- [<span data-ttu-id="658a3-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="658a3-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="658a3-120">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="658a3-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
