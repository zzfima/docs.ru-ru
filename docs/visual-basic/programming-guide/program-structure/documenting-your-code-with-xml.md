---
title: "Документирование кода с помощью XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0ce3f216f9e851feb0b3506b6ed1279b7d9479e7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="4c74e-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c74e-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="4c74e-103">В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], можно документировать код с помощью XML</span><span class="sxs-lookup"><span data-stu-id="4c74e-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="4c74e-104">Комментарии к XML-документации</span><span class="sxs-lookup"><span data-stu-id="4c74e-104">XML Documentation Comments</span></span>  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="4c74e-105">предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="4c74e-105"> provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="4c74e-106">Можно автоматически создавать XML – схему для типов и членов, а затем можно указать сводку, описательную документацию для каждого параметра и другие примечания.</span><span class="sxs-lookup"><span data-stu-id="4c74e-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="4c74e-107">С соответствующей настройкой автоматически создается XML-документации в XML-файл с тем же именем, как проект и расширением XML.</span><span class="sxs-lookup"><span data-stu-id="4c74e-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="4c74e-108">Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="4c74e-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="4c74e-109">XML-файл можно использовать или обрабатываться как XML.</span><span class="sxs-lookup"><span data-stu-id="4c74e-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="4c74e-110">Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.</span><span class="sxs-lookup"><span data-stu-id="4c74e-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="4c74e-111">XML – документация начинается с `'''`.</span><span class="sxs-lookup"><span data-stu-id="4c74e-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="4c74e-112">Обработка этих комментариев имеет некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="4c74e-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="4c74e-113">Документация должен иметь правильный формат XML.</span><span class="sxs-lookup"><span data-stu-id="4c74e-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="4c74e-114">Если XML не имеет правильного формата, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="4c74e-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="4c74e-115">Разработчики могут создавать свои собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="4c74e-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="4c74e-116">Существует рекомендуемый набор тегов (см. «Связанные разделы» в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="4c74e-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="4c74e-117">Некоторые Рекомендуемые теги имеют специальное значение:</span><span class="sxs-lookup"><span data-stu-id="4c74e-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="4c74e-118">\<Param настроек тег используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="4c74e-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="4c74e-119">Если используется, компилятор проверит, что параметр существует и что все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="4c74e-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="4c74e-120">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4c74e-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="4c74e-121">`cref` Атрибута можно прикрепить к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="4c74e-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="4c74e-122">Компилятор проверяет, что этот элемент кода существует.</span><span class="sxs-lookup"><span data-stu-id="4c74e-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="4c74e-123">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4c74e-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="4c74e-124">Компилятор также соблюдает любые `Imports` при поиске типа, описанного в инструкциях `cref` атрибута.</span><span class="sxs-lookup"><span data-stu-id="4c74e-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="4c74e-125">\<Сводка настроек тег используется технологией IntelliSense в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] для отображения дополнительных сведений о тип или член.</span><span class="sxs-lookup"><span data-stu-id="4c74e-125">The \<summary> tag is used by IntelliSense in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4c74e-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4c74e-126">Related Sections</span></span>  
 <span data-ttu-id="4c74e-127">Дополнительные сведения о создании файла XML с комментариями документации в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4c74e-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4c74e-128">/doc</span><span class="sxs-lookup"><span data-stu-id="4c74e-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="4c74e-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="4c74e-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="4c74e-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="4c74e-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="4c74e-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="4c74e-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="4c74e-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4c74e-132">XML Tools in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="4c74e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4c74e-133">See Also</span></span>  
 <span data-ttu-id="4c74e-134">[Разработка приложений с помощью Visual Basic](../../../visual-basic/developing-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c74e-134">[Developing Applications with Visual Basic](../../../visual-basic/developing-apps/index.md) </span></span>  
<span data-ttu-id="4c74e-135"> [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="4c74e-135"> [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)</span></span>
