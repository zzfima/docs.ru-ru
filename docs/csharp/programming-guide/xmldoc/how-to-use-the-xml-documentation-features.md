---
title: Использование XML-документации (руководство по программированию на C#)
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 5de94b1f1ab44f954b5bab9f8b5212c33325c19d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696718"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="55ac3-102">Практическое руководство. Использование XML-документации</span><span class="sxs-lookup"><span data-stu-id="55ac3-102">How to use the XML documentation features</span></span>

<span data-ttu-id="55ac3-103">В данном примере представлены основные общие сведения о задокументированном типе.</span><span class="sxs-lookup"><span data-stu-id="55ac3-103">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="55ac3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="55ac3-104">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="55ac3-105">В примере создается XML-файл со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="55ac3-105">The example generates an .xml file with the following contents:</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member 
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="55ac3-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="55ac3-106">Compiling the code</span></span>

<span data-ttu-id="55ac3-107">Чтобы скомпилировать этот пример, введите в командной строке:</span><span class="sxs-lookup"><span data-stu-id="55ac3-107">To compile the example, type the following command line:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="55ac3-108">Эта команда создает XML-файл *XMLsample.xml*, который можно просмотреть в браузере или с помощью команды TYPE.</span><span class="sxs-lookup"><span data-stu-id="55ac3-108">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the TYPE command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="55ac3-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="55ac3-109">Robust programming</span></span>

<span data-ttu-id="55ac3-110">Документация XML начинается с ///.</span><span class="sxs-lookup"><span data-stu-id="55ac3-110">XML documentation starts with ///.</span></span> <span data-ttu-id="55ac3-111">При создании нового проекта мастер добавляет несколько строк ///.</span><span class="sxs-lookup"><span data-stu-id="55ac3-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="55ac3-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="55ac3-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="55ac3-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="55ac3-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="55ac3-114">Если формат XML неверен, то выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="55ac3-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="55ac3-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="55ac3-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="55ac3-116">Существует рекомендуемый набор тегов (см. статью о [рекомендуемых тегах для комментариев документации](recommended-tags-for-documentation-comments.md)).</span><span class="sxs-lookup"><span data-stu-id="55ac3-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="55ac3-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="55ac3-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="55ac3-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="55ac3-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="55ac3-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="55ac3-119">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="55ac3-120">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="55ac3-120">If the verification failed, the compiler issues a warning.</span></span>

  - <span data-ttu-id="55ac3-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="55ac3-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="55ac3-122">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="55ac3-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="55ac3-123">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="55ac3-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="55ac3-124">Компилятор учитывает любые операторы `using` при поиске типа, описанного в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="55ac3-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="55ac3-125">Тег \<summary> используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="55ac3-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55ac3-126">XML-файл не предоставляет полную информацию о типе и членах (например, он не содержит никаких сведений о типе).</span><span class="sxs-lookup"><span data-stu-id="55ac3-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="55ac3-127">Чтобы получить полную информацию о типе или члене, необходимо использовать файл документации вместе с отражением на текущий тип или член.</span><span class="sxs-lookup"><span data-stu-id="55ac3-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="55ac3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="55ac3-128">See also</span></span>

- [<span data-ttu-id="55ac3-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="55ac3-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="55ac3-130">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="55ac3-130">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="55ac3-131">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="55ac3-131">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="55ac3-132">Обработчик документации DocFX</span><span class="sxs-lookup"><span data-stu-id="55ac3-132">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="55ac3-133">Обработчик документации Sandcastle</span><span class="sxs-lookup"><span data-stu-id="55ac3-133">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
