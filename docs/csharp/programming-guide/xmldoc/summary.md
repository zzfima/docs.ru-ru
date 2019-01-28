---
title: Руководство по программированию на C#. Тег &lt;summary&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5447b9ea129c26fdbb9effe1a3aeac6d7290764a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740038"
---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="56e0c-102">&lt;summary&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="56e0c-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="56e0c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56e0c-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56e0c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="56e0c-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="56e0c-105">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="56e0c-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56e0c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="56e0c-106">Remarks</span></span>  
 <span data-ttu-id="56e0c-107">Тег \<summary> следует использовать для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="56e0c-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="56e0c-108">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md).</span><span class="sxs-lookup"><span data-stu-id="56e0c-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="56e0c-109">Чтобы включить средства документации, такие как [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="56e0c-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="56e0c-110">Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="56e0c-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="56e0c-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="56e0c-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="56e0c-112">Для создания окончательной документации на основе сформированного компилятором файла можно создать пользовательское средство или использовать такое средство, как [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="56e0c-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e0c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="56e0c-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 <span data-ttu-id="56e0c-114">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="56e0c-114">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="56e0c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="56e0c-115">Example</span></span>  
 <span data-ttu-id="56e0c-116">В следующем примере показано, как создать ссылку `cref` на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="56e0c-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 <span data-ttu-id="56e0c-117">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="56e0c-117">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56e0c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="56e0c-118">See also</span></span>

- [<span data-ttu-id="56e0c-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="56e0c-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="56e0c-120">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="56e0c-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
