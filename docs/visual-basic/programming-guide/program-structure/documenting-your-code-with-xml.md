---
title: "Документирование кода с помощью XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ddb1f366002c4f0c675c591d83aab1b31ef8f602
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="dffa8-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dffa8-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="dffa8-103">В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], можно выполнять документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="dffa8-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="dffa8-104">Комментарии к XML-документации</span><span class="sxs-lookup"><span data-stu-id="dffa8-104">XML Documentation Comments</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="dffa8-105">предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="dffa8-105"> provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="dffa8-106">Можно автоматически создавать схема XML для типов и членов, а также введите сводку, описательную документацию для каждого параметра и другие примечания.</span><span class="sxs-lookup"><span data-stu-id="dffa8-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="dffa8-107">С соответствующей настройкой автоматически создается XML-документации в XML-файл с тем же именем, как проект и расширением XML.</span><span class="sxs-lookup"><span data-stu-id="dffa8-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="dffa8-108">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="dffa8-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="dffa8-109">XML-файл можно использовать или обрабатываться как XML.</span><span class="sxs-lookup"><span data-stu-id="dffa8-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="dffa8-110">Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.</span><span class="sxs-lookup"><span data-stu-id="dffa8-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="dffa8-111">XML-документации начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="dffa8-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="dffa8-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="dffa8-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="dffa8-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="dffa8-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="dffa8-114">Если XML не имеет правильного формата, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="dffa8-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="dffa8-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="dffa8-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="dffa8-116">Отсутствует рекомендуемый набор тегов (см. «Связанные разделы» в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="dffa8-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="dffa8-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="dffa8-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="dffa8-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="dffa8-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="dffa8-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="dffa8-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="dffa8-120">Если проверка завершается ошибкой, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="dffa8-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="dffa8-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="dffa8-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="dffa8-122">Компилятор проверяет, что этот элемент кода существует.</span><span class="sxs-lookup"><span data-stu-id="dffa8-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="dffa8-123">Если проверка завершается ошибкой, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="dffa8-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="dffa8-124">Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибута.</span><span class="sxs-lookup"><span data-stu-id="dffa8-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="dffa8-125">\<Сводки > тег используется технологией IntelliSense в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] для отображения дополнительных сведений о тип или член.</span><span class="sxs-lookup"><span data-stu-id="dffa8-125">The \<summary> tag is used by IntelliSense in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dffa8-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="dffa8-126">Related Sections</span></span>  
 <span data-ttu-id="dffa8-127">Дополнительные сведения о создании XML-файла в комментарии документации в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="dffa8-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="dffa8-128">/doc</span><span class="sxs-lookup"><span data-stu-id="dffa8-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="dffa8-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="dffa8-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="dffa8-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="dffa8-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="dffa8-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="dffa8-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="dffa8-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dffa8-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="dffa8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dffa8-133">See Also</span></span>  
 [<span data-ttu-id="dffa8-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dffa8-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="dffa8-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dffa8-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
