---
title: Документирование кода с помощью XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: b99c37f30d595e114bb4625a2881a9f0b463f5e6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524411"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="c7bb3-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7bb3-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="c7bb3-103">В Visual Basic можно документировать код с помощью XML</span><span class="sxs-lookup"><span data-stu-id="c7bb3-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="c7bb3-104">Комментарии к XML-документации</span><span class="sxs-lookup"><span data-stu-id="c7bb3-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="c7bb3-105">Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="c7bb3-106">Можно автоматически создавать схема XML для типов и членов и введите сводку, описательную документацию для каждого параметра и другие примечания.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="c7bb3-107">С соответствующей настройкой XML-документации автоматически генерируется в файл XML с именем проекта и расширение XML.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="c7bb3-108">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb3-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="c7bb3-109">XML-файле может быть использоваться или обрабатываться как XML.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="c7bb3-110">Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="c7bb3-111">Документация XML начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="c7bb3-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="c7bb3-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="c7bb3-114">Если XML-код сформирован неправильно, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="c7bb3-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="c7bb3-116">Есть рекомендуемый набор тегов (см. в разделе «Связанные разделы» этой статьи).</span><span class="sxs-lookup"><span data-stu-id="c7bb3-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="c7bb3-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="c7bb3-118">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="c7bb3-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="c7bb3-120">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="c7bb3-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="c7bb3-122">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="c7bb3-123">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="c7bb3-124">Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибута.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="c7bb3-125">\<Summary > тег используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типа или члена.</span><span class="sxs-lookup"><span data-stu-id="c7bb3-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7bb3-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c7bb3-126">Related Sections</span></span>  
 <span data-ttu-id="c7bb3-127">Дополнительные сведения о создании файла XML с комментариями документации см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="c7bb3-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c7bb3-128">/doc</span><span class="sxs-lookup"><span data-stu-id="c7bb3-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="c7bb3-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="c7bb3-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)  
  
-   [<span data-ttu-id="c7bb3-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="c7bb3-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="c7bb3-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="c7bb3-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="c7bb3-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7bb3-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="c7bb3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c7bb3-133">See Also</span></span>  
 [<span data-ttu-id="c7bb3-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7bb3-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="c7bb3-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7bb3-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
