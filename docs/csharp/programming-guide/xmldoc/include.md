---
title: <include> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 22d87559766c04e53141e843ee8768c8aab89a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156978"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="1ef61-102">Руководство по программированию на C# \<include></span><span class="sxs-lookup"><span data-stu-id="1ef61-102">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ef61-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ef61-103">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="1ef61-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ef61-104">Parameters</span></span>

- `filename`

  <span data-ttu-id="1ef61-105">Имя XML-файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="1ef61-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="1ef61-106">Имя файла может быть квалифицировано с помощью относительного пути к файлу исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1ef61-106">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="1ef61-107">`filename` необходимо заключать в одинарные кавычки (' ').</span><span class="sxs-lookup"><span data-stu-id="1ef61-107">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="1ef61-108">Путь тегов в `filename`, который ведет к тегу `name`.</span><span class="sxs-lookup"><span data-stu-id="1ef61-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="1ef61-109">Путь необходимо заключать в одинарные кавычки (' ').</span><span class="sxs-lookup"><span data-stu-id="1ef61-109">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="1ef61-110">Спецификатор имени в теге, предшествующий комментариям. `name` будет иметь идентификатор `id`.</span><span class="sxs-lookup"><span data-stu-id="1ef61-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

<span data-ttu-id="1ef61-111">Идентификатор тега, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="1ef61-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="1ef61-112">Идентификатор заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="1ef61-112">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="1ef61-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ef61-113">Remarks</span></span>

<span data-ttu-id="1ef61-114">Тег \<include> позволяет задать ссылку на комментарии в другом файле, которые описывают типы и члены вашего исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1ef61-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="1ef61-115">Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1ef61-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="1ef61-116">Помещая комментарии документации в отдельный файл, вы можете реализовать управление их версиями отдельно от версий исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1ef61-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="1ef61-117">В этом случае файл исходного кода может быть извлечен для изменения одним пользователем, а файл документации — другим.</span><span class="sxs-lookup"><span data-stu-id="1ef61-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="1ef61-118">Тег \<include> использует XML-синтаксис XPath.</span><span class="sxs-lookup"><span data-stu-id="1ef61-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="1ef61-119">Сведения об использовании тега \<include> см. в документации по XPath.</span><span class="sxs-lookup"><span data-stu-id="1ef61-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>

## <a name="example"></a><span data-ttu-id="1ef61-120">Пример</span><span class="sxs-lookup"><span data-stu-id="1ef61-120">Example</span></span>

<span data-ttu-id="1ef61-121">В этом примере представлено несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="1ef61-121">This is a multifile example.</span></span> <span data-ttu-id="1ef61-122">Ниже показан первый файл, в котором используется тег \<include>.</span><span class="sxs-lookup"><span data-stu-id="1ef61-122">The following is the first file, which uses \<include>.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="1ef61-123">Второй файл, *xml_include_tag.doc*, содержит следующие комментарии документации:</span><span class="sxs-lookup"><span data-stu-id="1ef61-123">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

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

## <a name="program-output"></a><span data-ttu-id="1ef61-124">Выходные данные программы</span><span class="sxs-lookup"><span data-stu-id="1ef61-124">Program output</span></span>

<span data-ttu-id="1ef61-125">При компиляции классов Test и Test2 с использованием следующей команды в командной строке создаются следующие выходные данные: `-doc:DocFileName.xml.` В Visual Studio параметр "Комментарии XML-документа" задается в области построения конструктора проектов.</span><span class="sxs-lookup"><span data-stu-id="1ef61-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="1ef61-126">При обнаружении тега \<include> компилятор C# ведет поиск комментариев документации в файле xml_include_tag.doc вместо текущего файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1ef61-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="1ef61-127">После этого компилятор создает файл DocFileName.xml, который будет использоваться средствами для работы с документацией, такими как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), для подготовки окончательной версии документации.</span><span class="sxs-lookup"><span data-stu-id="1ef61-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ef61-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ef61-128">See also</span></span>

- [<span data-ttu-id="1ef61-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1ef61-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1ef61-130">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="1ef61-130">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
