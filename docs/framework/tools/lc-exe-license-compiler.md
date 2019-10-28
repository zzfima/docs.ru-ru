---
title: Lc.exe (компилятор лицензий)
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 17ab7317ff1147dc79fae4ef3068cd9bc2143907
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774207"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="dec67-102">Lc.exe (компилятор лицензий)</span><span class="sxs-lookup"><span data-stu-id="dec67-102">Lc.exe (License Compiler)</span></span>
<span data-ttu-id="dec67-103">Компилятор лицензий считывает текстовые файлы, содержащие сведения о лицензиях, и создает двоичный файл, который может быть внедрен в исполняемый файл среды CLR в качестве ресурса.</span><span class="sxs-lookup"><span data-stu-id="dec67-103">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="dec67-104">Конструктор Windows Forms автоматически создает или обновляет текстовый LICX-файл при каждом добавлении лицензированного элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="dec67-104">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="dec67-105">В процессе компиляции система проектов преобразует текстовый LICX-файл в двоичный LICENSES-файл ресурсов, который обеспечивает лицензирование элементов управления .NET.</span><span class="sxs-lookup"><span data-stu-id="dec67-105">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="dec67-106">Двоичный файл ресурсов будет затем внедрен в выходной файл проекта.</span><span class="sxs-lookup"><span data-stu-id="dec67-106">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="dec67-107">При использовании компилятора лицензий во время создания проекта перекрестная компиляция между 32-разрядными и 64-разрядными системами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="dec67-107">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="dec67-108">Это происходит потому, что компилятор лицензий должен загружать сборки, а загрузка 64-разрядных сборок из 32-разрядного приложения и наоборот не допускается.</span><span class="sxs-lookup"><span data-stu-id="dec67-108">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="dec67-109">В этом случае запускайте компилятор лицензий из командной строки, чтобы скомпилировать лицензии вручную, и укажите соответствующую архитектуру.</span><span class="sxs-lookup"><span data-stu-id="dec67-109">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="dec67-110">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dec67-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="dec67-111">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="dec67-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="dec67-112">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="dec67-112">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="dec67-113">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="dec67-113">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec67-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dec67-114">Syntax</span></span>  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="dec67-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="dec67-115">Option</span></span>|<span data-ttu-id="dec67-116">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="dec67-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="dec67-117">**/complist:** *имя_файла*</span><span class="sxs-lookup"><span data-stu-id="dec67-117">**/complist:** *filename*</span></span>|<span data-ttu-id="dec67-118">Задает имя файла, который содержит список лицензируемых компонентов, включаемых в LICENSES-файл.</span><span class="sxs-lookup"><span data-stu-id="dec67-118">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="dec67-119">Для каждого компонента указывается его полное имя, в одной строке содержится только один компонент.</span><span class="sxs-lookup"><span data-stu-id="dec67-119">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="dec67-120">Пользователи, работающие с программой из командной строки, могут указать отдельный файл для каждой формы, входящей в проект.</span><span class="sxs-lookup"><span data-stu-id="dec67-120">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="dec67-121">Программа Lc.exe принимает несколько входных файлов и создает один LICENSES-файл.</span><span class="sxs-lookup"><span data-stu-id="dec67-121">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="dec67-122">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="dec67-122">**/h**[**elp**]</span></span>|<span data-ttu-id="dec67-123">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="dec67-123">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="dec67-124">**/i:** *модуль*</span><span class="sxs-lookup"><span data-stu-id="dec67-124">**/i:** *module*</span></span>|<span data-ttu-id="dec67-125">Задает модули, в которых содержатся компоненты, перечисленные в файле **/complist**.</span><span class="sxs-lookup"><span data-stu-id="dec67-125">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="dec67-126">Чтобы указать несколько модулей, используйте несколько флагов **/i**.</span><span class="sxs-lookup"><span data-stu-id="dec67-126">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="dec67-127">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="dec67-127">**/nologo**</span></span>|<span data-ttu-id="dec67-128">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="dec67-128">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="dec67-129">**/outdir:** *путь*</span><span class="sxs-lookup"><span data-stu-id="dec67-129">**/outdir:** *path*</span></span>|<span data-ttu-id="dec67-130">Задает каталог, в котором следует разместить полученные LICENSES-файлы.</span><span class="sxs-lookup"><span data-stu-id="dec67-130">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="dec67-131">**/target:** *целевой_PE*</span><span class="sxs-lookup"><span data-stu-id="dec67-131">**/target:** *targetPE*</span></span>|<span data-ttu-id="dec67-132">Задает исполняемый файл, для которого создается LICENSES-файл.</span><span class="sxs-lookup"><span data-stu-id="dec67-132">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="dec67-133">**/v**</span><span class="sxs-lookup"><span data-stu-id="dec67-133">**/v**</span></span>|<span data-ttu-id="dec67-134">Задает режим компиляции с выводом сведений о ходе процесса.</span><span class="sxs-lookup"><span data-stu-id="dec67-134">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="dec67-135">**@** *файл*</span><span class="sxs-lookup"><span data-stu-id="dec67-135">**@** *file*</span></span>|<span data-ttu-id="dec67-136">Задает файл ответов (RSP).</span><span class="sxs-lookup"><span data-stu-id="dec67-136">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="dec67-137">**/?**</span><span class="sxs-lookup"><span data-stu-id="dec67-137">**/?**</span></span>|<span data-ttu-id="dec67-138">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="dec67-138">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dec67-139">Пример</span><span class="sxs-lookup"><span data-stu-id="dec67-139">Example</span></span>  
  
1. <span data-ttu-id="dec67-140">Если применяется лицензированный элемент управления `MyCompany.Samples.LicControl1`, который содержится в библиотеке `Samples.DLL` приложения `HostApp.exe` *, `HostAppLic.txt` можно создать файл* , содержащий указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="dec67-140">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="dec67-141">Создайте LICENSES-файл с именем `HostApp.exe.licenses`, используя следующую команду.</span><span class="sxs-lookup"><span data-stu-id="dec67-141">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="dec67-142">Создайте `HostApp.exe`, включив в него LICENSES-файл в качестве ресурса.</span><span class="sxs-lookup"><span data-stu-id="dec67-142">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="dec67-143">Для создания приложения на языке C# используется следующая команда.</span><span class="sxs-lookup"><span data-stu-id="dec67-143">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="dec67-144">Следующая команда компилирует `myApp.licenses` из списков лицензированных компонентов, указанных файлами `hostapplic.txt` `hostapplic2.txt` и `hostapplic3.txt`.</span><span class="sxs-lookup"><span data-stu-id="dec67-144">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="dec67-145">Аргумент `modulesList` задает модули, в которых содержатся лицензируемые компоненты.</span><span class="sxs-lookup"><span data-stu-id="dec67-145">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="dec67-146">Пример файла ответов</span><span class="sxs-lookup"><span data-stu-id="dec67-146">Response File Example</span></span>  
 <span data-ttu-id="dec67-147">Ниже приведен пример файла ответов `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="dec67-147">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="dec67-148">Подробнее о файлах ответов см. в разделе [Файлы ответов](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="dec67-148">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt   
/i:WFCPrj.dll   
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="dec67-149">В приведенной ниже команде используется файл `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="dec67-149">The following command line uses the `response.rsp` file.</span></span>  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="dec67-150">См. также</span><span class="sxs-lookup"><span data-stu-id="dec67-150">See also</span></span>

- [<span data-ttu-id="dec67-151">Инструменты</span><span class="sxs-lookup"><span data-stu-id="dec67-151">Tools</span></span>](index.md)
- [<span data-ttu-id="dec67-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="dec67-152">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)
- [<span data-ttu-id="dec67-153">Командные строки</span><span class="sxs-lookup"><span data-stu-id="dec67-153">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
