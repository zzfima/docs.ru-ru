---
title: "&lt;summary&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <summary>
- summary
dev_langs:
- CSharp
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd96e58494196fcfdeb46e9e59481666ec9466f3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="54b70-102">&lt;summary&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="54b70-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="54b70-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54b70-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54b70-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="54b70-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="54b70-105">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="54b70-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b70-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="54b70-106">Remarks</span></span>  
 <span data-ttu-id="54b70-107">Тег \<summary> следует использовать для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="54b70-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="54b70-108">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md).</span><span class="sxs-lookup"><span data-stu-id="54b70-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="54b70-109">Чтобы включить средства документации, такие как [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="54b70-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="54b70-110">Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="54b70-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="54b70-111">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="54b70-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="54b70-112">Для создания окончательной документации на основе сформированного компилятором файла можно создать пользовательское средство или использовать такое средство, как [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="54b70-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b70-113">Пример</span><span class="sxs-lookup"><span data-stu-id="54b70-113">Example</span></span>  
 <span data-ttu-id="54b70-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="54b70-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]</span></span>  
  
 <span data-ttu-id="54b70-115">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="54b70-115">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="54b70-116">Пример</span><span class="sxs-lookup"><span data-stu-id="54b70-116">Example</span></span>  
 <span data-ttu-id="54b70-117">В следующем примере показано, как создать ссылку `cref` на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="54b70-117">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 <span data-ttu-id="54b70-118">[!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="54b70-118">[!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]</span></span>  
  
 <span data-ttu-id="54b70-119">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="54b70-119">The previous example produces the following XML file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54b70-120">См. также</span><span class="sxs-lookup"><span data-stu-id="54b70-120">See Also</span></span>  
 <span data-ttu-id="54b70-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="54b70-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="54b70-122">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="54b70-122">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

