---
title: -doc
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0948b9ef0675541ca595bb297e01e62c9d79a181
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-doc"></a><span data-ttu-id="13148-102">-doc</span><span class="sxs-lookup"><span data-stu-id="13148-102">-doc</span></span>
<span data-ttu-id="13148-103">Обрабатывает комментарии к документации в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="13148-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13148-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13148-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="13148-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="13148-105">Arguments</span></span>  
  
|<span data-ttu-id="13148-106">Термин</span><span class="sxs-lookup"><span data-stu-id="13148-106">Term</span></span>|<span data-ttu-id="13148-107">Определение</span><span class="sxs-lookup"><span data-stu-id="13148-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="13148-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="13148-108">`+` &#124; `-`</span></span>|<span data-ttu-id="13148-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="13148-109">Optional.</span></span> <span data-ttu-id="13148-110">Указание +, или просто `-doc`, компилятор создает документацию и поместите его в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="13148-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="13148-111">Указание `-` эквивалентно отсутствию `-doc`, вызывая нет сведений о документации.</span><span class="sxs-lookup"><span data-stu-id="13148-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="13148-112">Является обязательным, если используется параметр `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="13148-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="13148-113">Задает выходной файл XML, который заполняется комментарии из файлов исходного кода для компиляции.</span><span class="sxs-lookup"><span data-stu-id="13148-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="13148-114">Если имя файла содержит пробелы, следует заключить имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="13148-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13148-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="13148-115">Remarks</span></span>  
 <span data-ttu-id="13148-116">`-doc` Параметр элементы управления ли компилятор создает XML-файл, содержащий комментарии документации.</span><span class="sxs-lookup"><span data-stu-id="13148-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="13148-117">Если вы используете `-doc:file` синтаксис, `file` задает имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="13148-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="13148-118">Если вы используете `-doc` или `-doc+`, компилятор принимает имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором.</span><span class="sxs-lookup"><span data-stu-id="13148-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="13148-119">Если вы используете `-doc-` или не указывайте `-doc` , компилятор не создает XML-файл.</span><span class="sxs-lookup"><span data-stu-id="13148-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="13148-120">В файлах исходного кода комментариям документации могут предшествовать следующие определения:</span><span class="sxs-lookup"><span data-stu-id="13148-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="13148-121">Определяемые пользователем типы, такие как [класса](../../../visual-basic/language-reference/statements/class-statement.md) или [интерфейса](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="13148-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="13148-122">Члены, например поле, [событий](../../../visual-basic/language-reference/statements/event-statement.md), [свойство](../../../visual-basic/language-reference/statements/property-statement.md), [функция](../../../visual-basic/language-reference/statements/function-statement.md), или [подпрограммы](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="13148-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="13148-123">Чтобы использовать созданный XML-файл с [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) компонента, имя XML-файла совпадать с именем сборки, которую требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="13148-123">To use the generated XML file with the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="13148-124">Убедитесь, что XML-файл в том же каталоге, что и сборка, если ссылка на сборку в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] проекта, XML-файл был найден.</span><span class="sxs-lookup"><span data-stu-id="13148-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="13148-125">XML-файлы документации не требуются для работы для кода в проекте или в проектах, на которые имеются ссылки в проект IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="13148-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="13148-126">Если при компиляции `/target:module`, XML-файл содержит теги `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="13148-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="13148-127">Эти теги указывают имя файла, содержащего манифест сборки для выходного файла компиляции.</span><span class="sxs-lookup"><span data-stu-id="13148-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="13148-128">В разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) способы создания документации из комментариев в коде.</span><span class="sxs-lookup"><span data-stu-id="13148-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="13148-129">Set - doc в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="13148-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="13148-130">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="13148-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="13148-131">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="13148-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="13148-132">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="13148-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="13148-133">3.  Задайте значение в **создать XML-файл документации** поле.</span><span class="sxs-lookup"><span data-stu-id="13148-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="13148-134">Пример</span><span class="sxs-lookup"><span data-stu-id="13148-134">Example</span></span>  
 <span data-ttu-id="13148-135">В разделе [документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) образец.</span><span class="sxs-lookup"><span data-stu-id="13148-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13148-136">См. также</span><span class="sxs-lookup"><span data-stu-id="13148-136">See Also</span></span>  
 [<span data-ttu-id="13148-137">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="13148-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="13148-138">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="13148-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
