---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399781"
---
# <a name="-doc"></a><span data-ttu-id="ca48d-102">-doc</span><span class="sxs-lookup"><span data-stu-id="ca48d-102">-doc</span></span>
<span data-ttu-id="ca48d-103">Обрабатывает комментарии к документации в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="ca48d-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca48d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca48d-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ca48d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ca48d-105">Arguments</span></span>  
  
|<span data-ttu-id="ca48d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ca48d-106">Term</span></span>|<span data-ttu-id="ca48d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ca48d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ca48d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ca48d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="ca48d-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ca48d-109">Optional.</span></span> <span data-ttu-id="ca48d-110">Указание +, или просто `-doc`, компилятор создает документацию и поместите его в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="ca48d-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="ca48d-111">Указание `-` эквивалентно отсутствию `-doc`, вызывая нет сведений о документации.</span><span class="sxs-lookup"><span data-stu-id="ca48d-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="ca48d-112">Является обязательным, если используется параметр `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="ca48d-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="ca48d-113">Указывает выходной XML-файл, который заполняется комментариями из файлов исходного кода, компиляции.</span><span class="sxs-lookup"><span data-stu-id="ca48d-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="ca48d-114">Если имя файла содержит пробел, заключите его в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="ca48d-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca48d-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca48d-115">Remarks</span></span>  
 <span data-ttu-id="ca48d-116">`-doc` Определяет, допустимо ли компилятор создает XML-файл, содержащий комментарии к документации.</span><span class="sxs-lookup"><span data-stu-id="ca48d-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="ca48d-117">Если вы используете `-doc:file` синтаксис, `file` параметр указывает имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="ca48d-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="ca48d-118">Если вы используете `-doc` или `-doc+`, компилятор принимает имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором.</span><span class="sxs-lookup"><span data-stu-id="ca48d-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="ca48d-119">Если вы используете `-doc-` или не указывайте `-doc` параметр, компилятор не создает XML-файл.</span><span class="sxs-lookup"><span data-stu-id="ca48d-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="ca48d-120">В файлах исходного кода комментарии документации могут предшествовать следующие определения:</span><span class="sxs-lookup"><span data-stu-id="ca48d-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="ca48d-121">Определяемые пользователем типы, такие как [класс](../../../visual-basic/language-reference/statements/class-statement.md) или [интерфейса](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="ca48d-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="ca48d-122">Члены, например поле, [событий](../../../visual-basic/language-reference/statements/event-statement.md), [свойство](../../../visual-basic/language-reference/statements/property-statement.md), [функция](../../../visual-basic/language-reference/statements/function-statement.md), или [подпрограммы](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ca48d-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="ca48d-123">Чтобы использовать созданный XML-файл с помощью Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) компонентов, имя XML-файла совпадать с именем сборки, которую требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="ca48d-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="ca48d-124">Убедитесь, что XML-файл находится в том же каталоге, что и сборка, таким образом, чтобы при ссылке на сборку в проект Visual Studio, XML-файл находится также.</span><span class="sxs-lookup"><span data-stu-id="ca48d-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="ca48d-125">Файлы XML-документации не являются обязательными для работы для кода в проекте или в рамках проектов ссылается проект IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ca48d-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="ca48d-126">Если при компиляции `/target:module`, XML-файл содержит теги `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="ca48d-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="ca48d-127">Эти теги укажите имя файла, содержащего манифест сборки для выходного файла компиляции.</span><span class="sxs-lookup"><span data-stu-id="ca48d-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="ca48d-128">См. в разделе [теги для комментариев XML](../../../visual-basic/language-reference/xmldoc/index.md) способы создания документации из комментариев в коде.</span><span class="sxs-lookup"><span data-stu-id="ca48d-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="ca48d-129">Чтобы задать - doc в Visual Studio интегрированной среды разработки</span><span class="sxs-lookup"><span data-stu-id="ca48d-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ca48d-130">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ca48d-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ca48d-131">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca48d-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ca48d-132">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="ca48d-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ca48d-133">3.  Задайте значение в **создать XML-файл документации** поле.</span><span class="sxs-lookup"><span data-stu-id="ca48d-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ca48d-134">Пример</span><span class="sxs-lookup"><span data-stu-id="ca48d-134">Example</span></span>  
 <span data-ttu-id="ca48d-135">См. в разделе [документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) образец.</span><span class="sxs-lookup"><span data-stu-id="ca48d-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca48d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ca48d-136">See Also</span></span>  
 [<span data-ttu-id="ca48d-137">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ca48d-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ca48d-138">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="ca48d-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
