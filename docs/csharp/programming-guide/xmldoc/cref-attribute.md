---
title: Руководство по программированию на C#. Атрибут cref
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: d088e1fcd0a1d1910b1284909dccf7b7d7b1d479
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588164"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="e3cfa-102">Атрибут cref (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e3cfa-102">cref Attribute (C# Programming Guide)</span></span>
<span data-ttu-id="e3cfa-103">Атрибут `cref` в теге XML-документации означает "кодовая ссылка".</span><span class="sxs-lookup"><span data-stu-id="e3cfa-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="e3cfa-104">Он указывает, что текст внутри тега представляет собой элемент кода, например тип, метод или свойство.</span><span class="sxs-lookup"><span data-stu-id="e3cfa-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="e3cfa-105">Средства создания документации, такие как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), используют атрибуты `cref` для автоматического создания гиперссылок на страницу, где документирован тип или член.</span><span class="sxs-lookup"><span data-stu-id="e3cfa-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3cfa-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e3cfa-106">Example</span></span>  
 <span data-ttu-id="e3cfa-107">В следующем примере показаны атрибуты `cref`, используемые в тегах [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="e3cfa-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]  
  
 <span data-ttu-id="e3cfa-108">В результате компиляции программа создает следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="e3cfa-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="e3cfa-109">Обратите внимание, что атрибут `cref` метода `GetZero`, в частности, был преобразован компилятором в `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="e3cfa-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="e3cfa-110">Префикс "M:" означает "метод" и является условным обозначением, распознаваемым средствами документации, такими как DocFX и Sandcastle.</span><span class="sxs-lookup"><span data-stu-id="e3cfa-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="e3cfa-111">Полный список префиксов см. в разделе [Обработка XML-файла](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="e3cfa-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>CRefTest</name>  
    </assembly>  
    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.#ctor">  
            <summary>  
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.   
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">  
            <summary>  
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.   
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example>   
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
            <code>  
            class TestClass   
            {  
                static int Main()   
                {  
                    return GetZero();  
                }  
            }  
            </code>  
            </example>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">  
            <summary>  
            The GetGenericValue method.  
            </summary>  
            <remarks>   
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.  
            </remarks>  
        </member>  
        <member name="T:TestNamespace.GenericClass`1">  
            <summary>  
            GenericClass.  
            </summary>  
            <remarks>   
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.  
            </remarks>  
        </member>  
    </members>    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains two cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example> This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
            <code>  
            class TestClass   
            {  
                static int Main()   
                {  
                    return GetZero();  
                }  
            }  
            </code>  
            </example>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">  
            <summary>  
            The GetGenericValue method.  
            </summary>  
            <remarks>   
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.  
            </remarks>  
        </member>  
        <member name="T:TestNamespace.GenericClass`1">  
            <summary>  
            GenericClass.  
            </summary>  
            <remarks>   
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.  
            </remarks>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3cfa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e3cfa-112">See also</span></span>

- [<span data-ttu-id="e3cfa-113">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="e3cfa-113">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="e3cfa-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="e3cfa-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
