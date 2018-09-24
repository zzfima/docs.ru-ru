---
title: Комментарии к XML-документации (Руководство по программированию на C#)
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: ab4f8fae748455f96ca5ea0255658cc76dd14f97
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46519634"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="5d915-102">Комментарии к XML-документации (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5d915-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="5d915-103">В Visual C# можно создавать документацию для кода путем включения XML-элементов в специальные поля комментариев (начинающиеся с трех символов косой черты) в исходном коде непосредственно перед блоком кода, к которому относятся комментарии. Например:</span><span class="sxs-lookup"><span data-stu-id="5d915-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="5d915-104">При выполнении компиляции с параметром [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) компилятор осуществляет поиск всех тегов XML в исходном коде и создает XML-файл документации.</span><span class="sxs-lookup"><span data-stu-id="5d915-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="5d915-105">Для получения окончательной документации на основе созданного компилятором файла можно создать пользовательский инструмент или использовать инструмент [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="5d915-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="5d915-106">Для ссылки на XML-элементы (например, если функция обрабатывает определенные XML-элементы, которые требуется включить в комментарии XML-документации) можно использовать стандартный механизм заключения в скобки (`<` и `>`).</span><span class="sxs-lookup"><span data-stu-id="5d915-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="5d915-107">Для ссылки на универсальные идентификаторы в элементах ссылок кода (`cref`) можно использовать escape-символы (например, `cref="List&lt;T&gt;"`) или фигурные скобки (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="5d915-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="5d915-108">В особом случае компилятор анализирует фигурные скобки, как угловые, чтобы при ссылке на универсальные идентификаторы сделать комментарий документации менее громоздким.</span><span class="sxs-lookup"><span data-stu-id="5d915-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d915-109">Комментарии XML-документации не являются метаданными. Они не включаются в скомпилированную сборку, и поэтому не доступны посредством отражения.</span><span class="sxs-lookup"><span data-stu-id="5d915-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d915-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5d915-110">In This Section</span></span>  
  
-   [<span data-ttu-id="5d915-111">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5d915-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="5d915-112">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="5d915-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="5d915-113">Разделители для тегов документации</span><span class="sxs-lookup"><span data-stu-id="5d915-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="5d915-114">Практическое руководство. Использование XML-документации</span><span class="sxs-lookup"><span data-stu-id="5d915-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="5d915-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5d915-115">Related Sections</span></span>  
 <span data-ttu-id="5d915-116">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="5d915-116">For more information, see:</span></span>  
  
-   [<span data-ttu-id="5d915-117">/doc (обработка комментариев документации)</span><span class="sxs-lookup"><span data-stu-id="5d915-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d915-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5d915-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d915-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5d915-119">See Also</span></span>

- [<span data-ttu-id="5d915-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5d915-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
