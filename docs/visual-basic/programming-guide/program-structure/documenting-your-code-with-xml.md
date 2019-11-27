---
title: Документирование кода с помощью XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347443"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="c1d68-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1d68-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="c1d68-103">В Visual Basic можно документировать код с помощью XML</span><span class="sxs-lookup"><span data-stu-id="c1d68-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="c1d68-104">Комментарии к XML-документации</span><span class="sxs-lookup"><span data-stu-id="c1d68-104">XML Documentation Comments</span></span>

<span data-ttu-id="c1d68-105">Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="c1d68-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="c1d68-106">Можно автоматически создать XML-схему для типов и членов, а затем предоставить сводные данные, описательную документацию для каждого параметра и другие замечания.</span><span class="sxs-lookup"><span data-stu-id="c1d68-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="c1d68-107">При соответствующей настройке XML-документация автоматически отправляется в XML-файл с тем же именем, что и у проекта, и с расширением XML.</span><span class="sxs-lookup"><span data-stu-id="c1d68-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="c1d68-108">Дополнительные сведения см. в разделе [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c1d68-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="c1d68-109">XML-файл можно использовать или иным образом манипулировать как XML.</span><span class="sxs-lookup"><span data-stu-id="c1d68-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="c1d68-110">Этот файл находится в том же каталоге, что и файл Output. exe или. DLL проекта.</span><span class="sxs-lookup"><span data-stu-id="c1d68-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="c1d68-111">Документация по XML начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="c1d68-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="c1d68-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="c1d68-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="c1d68-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="c1d68-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="c1d68-114">Если XML сформирован неправильно, создается предупреждение, а файл документации содержит комментарий, в котором говорится, что обнаружена ошибка.</span><span class="sxs-lookup"><span data-stu-id="c1d68-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="c1d68-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="c1d68-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="c1d68-116">Рекомендуемый набор тегов (см. раздел "связанные разделы" в этой статье).</span><span class="sxs-lookup"><span data-stu-id="c1d68-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="c1d68-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="c1d68-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="c1d68-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="c1d68-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="c1d68-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="c1d68-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="c1d68-120">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c1d68-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="c1d68-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="c1d68-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="c1d68-122">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="c1d68-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="c1d68-123">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c1d68-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="c1d68-124">Компилятор также учитывает любые операторы `Imports` при поиске типа, описанного в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="c1d68-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="c1d68-125">Тег \<Summary > используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="c1d68-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c1d68-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c1d68-126">Related Sections</span></span>

<span data-ttu-id="c1d68-127">Дополнительные сведения о создании XML-файла с комментариями к документации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c1d68-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="c1d68-128">-doc</span><span class="sxs-lookup"><span data-stu-id="c1d68-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="c1d68-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="c1d68-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="c1d68-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="c1d68-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="c1d68-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="c1d68-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="c1d68-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1d68-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="c1d68-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c1d68-133">See also</span></span>

- [<span data-ttu-id="c1d68-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1d68-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="c1d68-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1d68-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
