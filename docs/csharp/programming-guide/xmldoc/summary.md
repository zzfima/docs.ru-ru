---
title: <summary> — Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 4a509c002bb6a55b4751712925ae7cc613911af2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587620"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="5f4df-102">\<summary> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5f4df-102">\<summary> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5f4df-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f4df-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f4df-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f4df-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5f4df-105">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="5f4df-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f4df-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f4df-106">Remarks</span></span>  
 <span data-ttu-id="5f4df-107">Тег \<summary> следует использовать для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="5f4df-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="5f4df-108">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](./remarks.md).</span><span class="sxs-lookup"><span data-stu-id="5f4df-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="5f4df-109">Чтобы включить средства документации, такие как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="5f4df-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="5f4df-110">Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="5f4df-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="5f4df-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5f4df-111">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="5f4df-112">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="5f4df-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f4df-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5f4df-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
 <span data-ttu-id="5f4df-114">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="5f4df-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="5f4df-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5f4df-115">Example</span></span>  
 <span data-ttu-id="5f4df-116">В следующем примере показано, как создать ссылку `cref` на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="5f4df-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]  
  
 <span data-ttu-id="5f4df-117">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="5f4df-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f4df-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5f4df-118">See also</span></span>

- [<span data-ttu-id="5f4df-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5f4df-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5f4df-120">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5f4df-120">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
