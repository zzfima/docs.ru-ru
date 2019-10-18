---
title: Документирование кода с помощью XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 58c8716450fd8310b81050c86dc297c5b7527761
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524502"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="d9e69-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9e69-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="d9e69-103">В Visual Basic можно документировать код с помощью XML</span><span class="sxs-lookup"><span data-stu-id="d9e69-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="d9e69-104">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="d9e69-104">XML Documentation Comments</span></span>

<span data-ttu-id="d9e69-105">Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="d9e69-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="d9e69-106">Можно автоматически создать XML-схему для типов и членов, а затем предоставить сводные данные, описательную документацию для каждого параметра и другие замечания.</span><span class="sxs-lookup"><span data-stu-id="d9e69-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="d9e69-107">При соответствующей настройке XML-документация автоматически отправляется в XML-файл с тем же именем, что и у проекта, и с расширением XML.</span><span class="sxs-lookup"><span data-stu-id="d9e69-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="d9e69-108">Дополнительные сведения см. в разделе [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d9e69-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="d9e69-109">XML-файл можно использовать или иным образом манипулировать как XML.</span><span class="sxs-lookup"><span data-stu-id="d9e69-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="d9e69-110">Этот файл находится в том же каталоге, что и файл Output. exe или. DLL проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e69-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="d9e69-111">Документация по XML начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="d9e69-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="d9e69-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="d9e69-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="d9e69-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="d9e69-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="d9e69-114">Если XML сформирован неправильно, создается предупреждение, а файл документации содержит комментарий, в котором говорится, что обнаружена ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9e69-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="d9e69-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="d9e69-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="d9e69-116">Рекомендуемый набор тегов (см. раздел "связанные разделы" в этой статье).</span><span class="sxs-lookup"><span data-stu-id="d9e69-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="d9e69-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="d9e69-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="d9e69-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="d9e69-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="d9e69-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="d9e69-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="d9e69-120">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d9e69-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="d9e69-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="d9e69-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="d9e69-122">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="d9e69-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="d9e69-123">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d9e69-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="d9e69-124">Компилятор также учитывает любые операторы `Imports` при поиске типа, описанного в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="d9e69-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="d9e69-125">Тег \<summary > используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="d9e69-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d9e69-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d9e69-126">Related Sections</span></span>

<span data-ttu-id="d9e69-127">Дополнительные сведения о создании XML-файла с комментариями к документации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d9e69-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="d9e69-128">-doc</span><span class="sxs-lookup"><span data-stu-id="d9e69-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="d9e69-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d9e69-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="d9e69-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="d9e69-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="d9e69-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="d9e69-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="d9e69-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9e69-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="d9e69-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d9e69-133">See also</span></span>

- [<span data-ttu-id="d9e69-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9e69-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="d9e69-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9e69-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
