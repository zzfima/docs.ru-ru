---
title: "XSLT-компилятор (xsltc.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b4ede7bdb8dad65e9cd959dfaa2f8956a877762
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-compiler-xsltcexe"></a><span data-ttu-id="52fd4-102">XSLT-компилятор (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="52fd4-102">XSLT Compiler (xsltc.exe)</span></span>
<span data-ttu-id="52fd4-103">XSLT-компилятор (xsltc.exe) компилирует таблицы стилей XSLT и создает сборку.</span><span class="sxs-lookup"><span data-stu-id="52fd4-103">The XSLT compiler (xsltc.exe) compiles XSLT style sheets and generates an assembly.</span></span> <span data-ttu-id="52fd4-104">Скомпилированную таблицу стилей можно передать непосредственно методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52fd4-104">The compiled style sheet can then be passed directly into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="52fd4-105">Подписанные сборки не могут создаваться с помощью xsltc.exe.</span><span class="sxs-lookup"><span data-stu-id="52fd4-105">You cannot generate signed assemblies with xsltc.exe.</span></span>  
  
 <span data-ttu-id="52fd4-106">Средство xsltc.exe входит в состав среды Visual Studio 2008.</span><span class="sxs-lookup"><span data-stu-id="52fd4-106">The xsltc.exe tool is included with Visual Studio 2008.</span></span> <span data-ttu-id="52fd4-107">Дополнительные сведения см. в разделе [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkId=89463).</span><span class="sxs-lookup"><span data-stu-id="52fd4-107">For more information, see the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52fd4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52fd4-108">Syntax</span></span>  
  
```  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a><span data-ttu-id="52fd4-109">Аргумент</span><span class="sxs-lookup"><span data-stu-id="52fd4-109">Argument</span></span>  
  
|<span data-ttu-id="52fd4-110">Аргумент</span><span class="sxs-lookup"><span data-stu-id="52fd4-110">Argument</span></span>|<span data-ttu-id="52fd4-111">Описание</span><span class="sxs-lookup"><span data-stu-id="52fd4-111">Description</span></span>|  
|--------------|-----------------|  
|`sourceFile`|<span data-ttu-id="52fd4-112">Задает имя таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-112">Specifies the name of the style sheet.</span></span> <span data-ttu-id="52fd4-113">Таблица стилей должна быть локальным файлом или располагаться в интрасети.</span><span class="sxs-lookup"><span data-stu-id="52fd4-113">The style sheet must be a local file or be located on the intranet.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="52fd4-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="52fd4-114">Options</span></span>  
  
|<span data-ttu-id="52fd4-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="52fd4-115">Option</span></span>|<span data-ttu-id="52fd4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="52fd4-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="52fd4-117">`/c[lass]:` `name`</span><span class="sxs-lookup"><span data-stu-id="52fd4-117">`/c[lass]:` `name`</span></span>|<span data-ttu-id="52fd4-118">Задает имя класса для следующей таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-118">Specifies the name of the class for the following style sheet.</span></span> <span data-ttu-id="52fd4-119">Имя класса может быть полным.</span><span class="sxs-lookup"><span data-stu-id="52fd4-119">The class name can be fully qualified.</span></span><br /><br /> <span data-ttu-id="52fd4-120">По умолчанию для имени класса используется имя таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-120">The class name defaults to the name of the style sheet.</span></span> <span data-ttu-id="52fd4-121">Например, если компилируется таблица стилей customers.xsl, по умолчанию используется имя класса customers.</span><span class="sxs-lookup"><span data-stu-id="52fd4-121">For example, if the style sheet customers.xsl is compiled, the default class name is customers.</span></span>|  
|<span data-ttu-id="52fd4-122">`/debug[`+&#124;-`]`</span><span class="sxs-lookup"><span data-stu-id="52fd4-122">`/debug[`+&#124;-`]`</span></span>|<span data-ttu-id="52fd4-123">Указывает, создаются ли отладочные сведения.</span><span class="sxs-lookup"><span data-stu-id="52fd4-123">Specifies whether to generate debugging information.</span></span><br /><br /> <span data-ttu-id="52fd4-124">Задание значения `+` или `/debug` включает создание компилятором отладочных сведений, которые размещаются в файле базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="52fd4-124">Specifying `+` or `/debug`, causes the compiler to generate debugging information and put it in a program database (PDB) file.</span></span> <span data-ttu-id="52fd4-125">Создаваемый PDB-файл получает имя `assemblyName`.pdb.</span><span class="sxs-lookup"><span data-stu-id="52fd4-125">The name of the generated PDB file is `assemblyName`.pdb.</span></span><br /><br /> <span data-ttu-id="52fd4-126">Если задано значение `-`, которое действует, если не указан параметр `/debug`, то отладочные данные не создаются.</span><span class="sxs-lookup"><span data-stu-id="52fd4-126">Specifying `-`, which is in effect if you do not specify `/debug`, causes no debug information to be created.</span></span> <span data-ttu-id="52fd4-127">Создается конечная версия сборки.</span><span class="sxs-lookup"><span data-stu-id="52fd4-127">A retail assembly is generated.</span></span> <span data-ttu-id="52fd4-128">**Примечание:** компиляция в режиме отладки может значительно снизить производительность XSLT.</span><span class="sxs-lookup"><span data-stu-id="52fd4-128">**Note:**  Compiling in debug mode can affect XSLT performance significantly.</span></span>|  
|`/help`|<span data-ttu-id="52fd4-129">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="52fd4-129">Displays command syntax and options for the tool.</span></span>|  
|`/nologo`|<span data-ttu-id="52fd4-130">Отключает вывод сообщения об авторских правах для компилятора.</span><span class="sxs-lookup"><span data-stu-id="52fd4-130">Suppresses the compiler copyright message from displaying.</span></span>|  
|<span data-ttu-id="52fd4-131">`/platform:` `string`</span><span class="sxs-lookup"><span data-stu-id="52fd4-131">`/platform:` `string`</span></span>|<span data-ttu-id="52fd4-132">Задает платформы, на которых может работать сборка.</span><span class="sxs-lookup"><span data-stu-id="52fd4-132">Specifies the platforms that the assembly can be run on.</span></span> <span data-ttu-id="52fd4-133">Далее описаны допустимые значения платформ:</span><span class="sxs-lookup"><span data-stu-id="52fd4-133">The following describes the valid platform values:</span></span><br /><br /> <span data-ttu-id="52fd4-134">`x86` - сборка компилируется для работы в 32-разрядной среде CLR, совместимой с архитектурой x86;</span><span class="sxs-lookup"><span data-stu-id="52fd4-134">`x86` compiles your assembly to be run by the 32-bit, x86-compatible common language runtime</span></span><br /><br /> <span data-ttu-id="52fd4-135">`x64` - сборка компилируется для работы в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций AMD64 или EM64T;</span><span class="sxs-lookup"><span data-stu-id="52fd4-135">`x64` compiles your assembly to be run by the 64-bit common language runtime on a computer that supports the AMD64 or EM64T instruction set.</span></span><br /><br /> [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)]<span data-ttu-id="52fd4-136">Компилирует сборку для выполнения в 64-разрядной среде CLR на компьютере, где [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] процессора.</span><span class="sxs-lookup"><span data-stu-id="52fd4-136"> compiles your assembly to be run by the 64-bit common language runtime on a computer that has an [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] processor.</span></span><br /><br /> <span data-ttu-id="52fd4-137">`anycpu` - сборка компилируется для работы на любой платформе</span><span class="sxs-lookup"><span data-stu-id="52fd4-137">`anycpu` compiles your assembly to run on any platform.</span></span> <span data-ttu-id="52fd4-138">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="52fd4-138">This is the default.</span></span>|  
|<span data-ttu-id="52fd4-139">`/out:` `assemblyName`</span><span class="sxs-lookup"><span data-stu-id="52fd4-139">`/out:` `assemblyName`</span></span>|<span data-ttu-id="52fd4-140">Задает имя выводимой сборки.</span><span class="sxs-lookup"><span data-stu-id="52fd4-140">Specifies the name of the assembly that is output.</span></span> <span data-ttu-id="52fd4-141">По умолчанию имя сборки совпадает с именем главной таблицы стилей или первой таблицы стилей, если присутствует несколько таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-141">The assembly name defaults to the name of the main style sheet or the first style sheet if multiple style sheets are present.</span></span><br /><br /> <span data-ttu-id="52fd4-142">Если таблица стилей содержит скрипты, они сохраняются в отдельной сборке.</span><span class="sxs-lookup"><span data-stu-id="52fd4-142">If the style sheet contains scripts, the scripts are saved to a separate assembly.</span></span> <span data-ttu-id="52fd4-143">Имена сборок скриптов формируются из имени главной сборки.</span><span class="sxs-lookup"><span data-stu-id="52fd4-143">Script assembly names are generated from the main assembly name.</span></span> <span data-ttu-id="52fd4-144">Например, если для имени сборки указано CustOrders.dll, первая сборка скрипта получит имя CustOrders_Script1.dll.</span><span class="sxs-lookup"><span data-stu-id="52fd4-144">For example, if you specified CustOrders.dll for your assembly name, the first script assembly is named CustOrders_Script1.dll.</span></span>|  
|<span data-ttu-id="52fd4-145">`/settings:` `document+-, script+-, DTD+-,`</span><span class="sxs-lookup"><span data-stu-id="52fd4-145">`/settings:` `document+-, script+-, DTD+-,`</span></span>|<span data-ttu-id="52fd4-146">Указывает, допускаются ли в таблице стилей функции `document()`, скрипт XSLT или DTD.</span><span class="sxs-lookup"><span data-stu-id="52fd4-146">Specifies whether to allow `document()` functions, XSLT script, or document type definition (DTD) in the style sheet.</span></span><br /><br /> <span data-ttu-id="52fd4-147">По умолчанию поддержка DTD, функции `document()` и скриптов отключена.</span><span class="sxs-lookup"><span data-stu-id="52fd4-147">The default behavior disables support for DTD, the `document()` function and scripting.</span></span>|  
|<span data-ttu-id="52fd4-148">`@` `file`</span><span class="sxs-lookup"><span data-stu-id="52fd4-148">`@` `file`</span></span>|<span data-ttu-id="52fd4-149">Позволяет указать файл, содержащий параметры компилятора.</span><span class="sxs-lookup"><span data-stu-id="52fd4-149">Lets you specify a file that contains the compiler options.</span></span>|  
|`?`|<span data-ttu-id="52fd4-150">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="52fd4-150">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52fd4-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="52fd4-151">Remarks</span></span>  
 <span data-ttu-id="52fd4-152">Решения XSLT могут состоять из нескольких модулей таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-152">XSLT solutions can consist of multiple style sheet modules.</span></span> <span data-ttu-id="52fd4-153">Программа xsltc.exe создает сборки из таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="52fd4-153">The xsltc.exe tool generates assemblies from style sheets.</span></span> <span data-ttu-id="52fd4-154">Затем эти сборки можно передать методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52fd4-154">The assemblies can then be passed into the <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="52fd4-155">Это может снизить затраты производительности в некоторых сценариях развертывания XSLT.</span><span class="sxs-lookup"><span data-stu-id="52fd4-155">This can help decrease performance costs in some XSLT deployment scenarios.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52fd4-156">Необходимо также включить в приложение скомпилированную сборку в виде ссылки.</span><span class="sxs-lookup"><span data-stu-id="52fd4-156">You must also include the compiled assembly as a reference in your application.</span></span>  
  
 <span data-ttu-id="52fd4-157">Средство xsltc.exe не проверяет класс (`/class:``name`) или сборки (`/out:``assemblyName`) имена.</span><span class="sxs-lookup"><span data-stu-id="52fd4-157">The xsltc.exe tool does not validate the class (`/class:``name`) or assembly (`/out:``assemblyName`) names.</span></span> <span data-ttu-id="52fd4-158">Если имена оказываются недопустимыми, среда CLR сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="52fd4-158">Errors are thrown by the common language runtime if the names are not valid.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="52fd4-159">Примеры</span><span class="sxs-lookup"><span data-stu-id="52fd4-159">Examples</span></span>  
 <span data-ttu-id="52fd4-160">Следующая команда компилирует таблицу стилей и создает сборку с именем booksort.dll.</span><span class="sxs-lookup"><span data-stu-id="52fd4-160">The following command compiles the style sheet and creates an assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl  
```  
  
 <span data-ttu-id="52fd4-161">Следующая команда компилирует таблицу стилей и создает сборку и PDB-файл, которые называются booksort.dll и booksort.pdb соответственно.</span><span class="sxs-lookup"><span data-stu-id="52fd4-161">The following command compiles the style sheet and creates an assembly and PDB file that are named booksort.dll and booksort.pdb respectively.</span></span>  
  
```  
xsltc booksort.xsl /debug  
```  
  
 <span data-ttu-id="52fd4-162">Следующая команда компилирует таблицу стилей, содержащую элемент msxsl:script, и создает две сборки с именами calc.dll и calc_Script1.dll.</span><span class="sxs-lookup"><span data-stu-id="52fd4-162">The following command compiles a style sheet that contains an msxsl:script element and creates two assemblies named calc.dll and calc_Script1.dll.</span></span>  
  
```  
xsltc /settings:script+ calc.xsl  
```  
  
 <span data-ttu-id="52fd4-163">Следующая команда включает обработку DTD и поддержку скриптов, а затем создает две сборки с именами myTest.dll и myTest_Script1.dll.</span><span class="sxs-lookup"><span data-stu-id="52fd4-163">The following command enables DTD processing and script support and creates two assemblies named myTest.dll and myTest_Script1.dll.</span></span>  
  
```  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 <span data-ttu-id="52fd4-164">Следующая команда компилирует два модуля таблицы стилей и создает одну сборку с именем booksort.dll.</span><span class="sxs-lookup"><span data-stu-id="52fd4-164">The following command compiles two style sheet modules and creates a single assembly named booksort.dll.</span></span>  
  
```  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a><span data-ttu-id="52fd4-165">См. также</span><span class="sxs-lookup"><span data-stu-id="52fd4-165">See Also</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [<span data-ttu-id="52fd4-166">Как: выполнить XSLT-преобразование с помощью сборки</span><span class="sxs-lookup"><span data-stu-id="52fd4-166">How to: Perform an XSLT Transformation by Using an Assembly</span></span>](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)  
 [<span data-ttu-id="52fd4-167">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="52fd4-167">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
