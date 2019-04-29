---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 13005eb55b430f6ff9b3a6408582a02e53838742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969212"
---
# <a name="-doc"></a><span data-ttu-id="b00b2-102">-doc</span><span class="sxs-lookup"><span data-stu-id="b00b2-102">-doc</span></span>
<span data-ttu-id="b00b2-103">Обрабатывает комментарии к документации в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="b00b2-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b00b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b00b2-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b00b2-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b00b2-105">Arguments</span></span>  
  
|<span data-ttu-id="b00b2-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b00b2-106">Term</span></span>|<span data-ttu-id="b00b2-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b00b2-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b00b2-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b00b2-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b00b2-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b00b2-109">Optional.</span></span> <span data-ttu-id="b00b2-110">Если задать + или `-doc`, компилятор создаст документацию и поместит ее в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="b00b2-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="b00b2-111">Если задать `-`, что эквивалентно отсутствию `-doc`, компилятор не будет создавать документацию.</span><span class="sxs-lookup"><span data-stu-id="b00b2-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="b00b2-112">Является обязательным, если используется параметр `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="b00b2-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="b00b2-113">Определяет выходной XML-файл, который заполняется комментариями из файлов исходного кода, участвующих в компиляции.</span><span class="sxs-lookup"><span data-stu-id="b00b2-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="b00b2-114">Если имя файла содержит пробел, заключите его в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="b00b2-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b00b2-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="b00b2-115">Remarks</span></span>  
 <span data-ttu-id="b00b2-116">Параметр `-doc` определяет, будет ли компилятор создавать XML-файл, содержащий комментарии.</span><span class="sxs-lookup"><span data-stu-id="b00b2-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="b00b2-117">Если вы используете синтаксис `-doc:file`, параметр `file` определяет имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="b00b2-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="b00b2-118">Если вы используете `-doc` или `-doc+`, компилятор использует имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором.</span><span class="sxs-lookup"><span data-stu-id="b00b2-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="b00b2-119">Если вы используете `-doc-` или не задаете параметр `-doc`, компилятор не создает XML-файл.</span><span class="sxs-lookup"><span data-stu-id="b00b2-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="b00b2-120">В файлах исходного кода комментарии к документации могут предшествовать таким определениям:</span><span class="sxs-lookup"><span data-stu-id="b00b2-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="b00b2-121">определяемые пользователем типы, такие как [class](../../../visual-basic/language-reference/statements/class-statement.md) или [interface](../../../visual-basic/language-reference/statements/interface-statement.md);</span><span class="sxs-lookup"><span data-stu-id="b00b2-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="b00b2-122">члены, такие как field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md) или [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b00b2-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="b00b2-123">Чтобы использовать созданный XML-файл с помощью такой функции Visual Studio, как [IntelliSense](/visualstudio/ide/using-intellisense), имя XML-файла должно совпадать с именем сборки.</span><span class="sxs-lookup"><span data-stu-id="b00b2-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="b00b2-124">Убедитесь, что XML-файл находится в том же каталоге, что и сборка, чтобы при обращении к сборке в проекте Visual Studio XML-файл мог бы также быть найден.</span><span class="sxs-lookup"><span data-stu-id="b00b2-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="b00b2-125">XML-файлы документации не являются обязательными для работы IntelliSense с кодом в рамках одного или нескольких проектов, на которые ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="b00b2-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="b00b2-126">XML-файл содержит теги `<assembly></assembly>`, если сборка не выполняется с помощью `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="b00b2-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="b00b2-127">Эти теги указывают имя файла, содержащего манифест сборки для выходного файла компиляции.</span><span class="sxs-lookup"><span data-stu-id="b00b2-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="b00b2-128">Способы создания документации из комментариев в коде описаны в разделе об [XML-тегах комментариев](../../../visual-basic/language-reference/xmldoc/index.md).</span><span class="sxs-lookup"><span data-stu-id="b00b2-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="b00b2-129">Настройка параметра -doc в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b00b2-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b00b2-130">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b00b2-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b00b2-131">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b00b2-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="b00b2-132">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="b00b2-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="b00b2-133">3.  Задайте значение в поле **Создать XML-файл документации**.</span><span class="sxs-lookup"><span data-stu-id="b00b2-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b00b2-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b00b2-134">Example</span></span>  
 <span data-ttu-id="b00b2-135">Пример см. в статье [Документирование кода с помощью XML-комментариев](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b00b2-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00b2-136">См. также</span><span class="sxs-lookup"><span data-stu-id="b00b2-136">See also</span></span>

- [<span data-ttu-id="b00b2-137">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b00b2-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b00b2-138">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="b00b2-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
