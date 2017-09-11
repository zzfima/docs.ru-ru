---
title: "&lt;include&gt; (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- CSharp
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0cabcc25c4e35027c600e4af2bccfad7f9db1514
ms.contentlocale: ru-ru
ms.lasthandoff: 08/29/2017

---
# <a name="ltincludegt-c-programming-guide"></a><span data-ttu-id="4d2c2-102">&lt;include&gt; (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4d2c2-102">&lt;include&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4d2c2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d2c2-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d2c2-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d2c2-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="4d2c2-105">Имя XML-файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="4d2c2-106">Имя файла может быть дополнено с указанием пути.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-106">The file name can be qualified with a path.</span></span> <span data-ttu-id="4d2c2-107">`filename` необходимо заключать в одинарные кавычки (' ').</span><span class="sxs-lookup"><span data-stu-id="4d2c2-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="4d2c2-108">Путь тегов в `filename`, который ведет к тегу `name`.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="4d2c2-109">Путь необходимо заключать в одинарные кавычки (' ').</span><span class="sxs-lookup"><span data-stu-id="4d2c2-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="4d2c2-110">Спецификатор имени в теге, предшествующий комментариям. `name` будет иметь идентификатор `id`.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="4d2c2-111">Идентификатор тега, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="4d2c2-112">Идентификатор заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="4d2c2-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d2c2-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d2c2-113">Remarks</span></span>  
 <span data-ttu-id="4d2c2-114">Тег \<include> позволяет задать ссылку на комментарии в другом файле, которые описывают типы и члены вашего исходного кода.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="4d2c2-115">Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="4d2c2-116">Помещая комментарии документации в отдельный файл, вы можете реализовать управление их версиями отдельно от версий исходного кода.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="4d2c2-117">В этом случае файл исходного кода может быть извлечен для изменения одним пользователем, а файл документации — другим.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="4d2c2-118">Тег \<include> использует XML-синтаксис XPath.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="4d2c2-119">Сведения об использовании тега \<include> см. в документации по XPath.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d2c2-120">Пример</span><span class="sxs-lookup"><span data-stu-id="4d2c2-120">Example</span></span>  
 <span data-ttu-id="4d2c2-121">В этом примере представлено несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-121">This is a multifile example.</span></span> <span data-ttu-id="4d2c2-122">Ниже показан первый файл, в котором используется тег \<include>:</span><span class="sxs-lookup"><span data-stu-id="4d2c2-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 <span data-ttu-id="4d2c2-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4d2c2-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span></span>  
  
 <span data-ttu-id="4d2c2-124">Второй файл (xml_include_tag.doc) содержит следующие комментарии документации:</span><span class="sxs-lookup"><span data-stu-id="4d2c2-124">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a><span data-ttu-id="4d2c2-125">Выходные данные программы</span><span class="sxs-lookup"><span data-stu-id="4d2c2-125">Program Output</span></span>  
 <span data-ttu-id="4d2c2-126">При компиляции классов Test и Test2 с использованием следующей команды в командной строке создаются следующие выходные данные: `/doc:DocFileName.xml.` В Visual Studio параметр "Комментарии XML-документа" задается в области построения конструктора проектов.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-126">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="4d2c2-127">При обнаружении тега \<include> компилятор C# ведет поиск комментариев документации в файле xml_include_tag.doc вместо текущего файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-127">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="4d2c2-128">После этого компилятор создает файл DocFileName.xml, который будет использоваться средствами для работы с документацией, такими как [Sandcastle](https://github.com/EWSoftware/SHFB), для подготовки окончательной версии документации.</span><span class="sxs-lookup"><span data-stu-id="4d2c2-128">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a><span data-ttu-id="4d2c2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4d2c2-129">See Also</span></span>  
 <span data-ttu-id="4d2c2-130">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d2c2-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4d2c2-131">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4d2c2-131">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

