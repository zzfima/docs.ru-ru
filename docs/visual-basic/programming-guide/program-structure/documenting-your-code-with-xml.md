---
title: Документирование кода с помощью XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d132fa514008d072158a0e6bedaff511c55b18c0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="eafc5-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eafc5-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="eafc5-103">В Visual Basic можно выполнять документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="eafc5-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="eafc5-104">Комментарии к XML-документации</span><span class="sxs-lookup"><span data-stu-id="eafc5-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="eafc5-105">Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="eafc5-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="eafc5-106">Можно автоматически создавать схема XML для типов и членов, а также введите сводку, описательную документацию для каждого параметра и другие примечания.</span><span class="sxs-lookup"><span data-stu-id="eafc5-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="eafc5-107">С соответствующей настройкой автоматически создается XML-документации в XML-файл с тем же именем, как проект и расширением XML.</span><span class="sxs-lookup"><span data-stu-id="eafc5-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="eafc5-108">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="eafc5-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="eafc5-109">XML-файл можно использовать или обрабатываться как XML.</span><span class="sxs-lookup"><span data-stu-id="eafc5-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="eafc5-110">Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.</span><span class="sxs-lookup"><span data-stu-id="eafc5-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="eafc5-111">XML-документации начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="eafc5-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="eafc5-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="eafc5-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="eafc5-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="eafc5-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="eafc5-114">Если XML не имеет правильного формата, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="eafc5-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="eafc5-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="eafc5-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="eafc5-116">Отсутствует рекомендуемый набор тегов (см. «Связанные разделы» в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="eafc5-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="eafc5-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="eafc5-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="eafc5-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="eafc5-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="eafc5-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="eafc5-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="eafc5-120">Если проверка завершается ошибкой, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="eafc5-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="eafc5-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="eafc5-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="eafc5-122">Компилятор проверяет, что этот элемент кода существует.</span><span class="sxs-lookup"><span data-stu-id="eafc5-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="eafc5-123">Если проверка завершается ошибкой, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="eafc5-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="eafc5-124">Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибута.</span><span class="sxs-lookup"><span data-stu-id="eafc5-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="eafc5-125">\<Сводки > тег используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о тип или член.</span><span class="sxs-lookup"><span data-stu-id="eafc5-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eafc5-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eafc5-126">Related Sections</span></span>  
 <span data-ttu-id="eafc5-127">Дополнительные сведения о создании XML-файла в комментарии документации в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="eafc5-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="eafc5-128">/doc</span><span class="sxs-lookup"><span data-stu-id="eafc5-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="eafc5-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="eafc5-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="eafc5-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="eafc5-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="eafc5-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="eafc5-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="eafc5-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eafc5-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="eafc5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="eafc5-133">See Also</span></span>  
 [<span data-ttu-id="eafc5-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eafc5-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="eafc5-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eafc5-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
