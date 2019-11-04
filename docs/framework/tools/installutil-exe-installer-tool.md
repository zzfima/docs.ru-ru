---
title: Installutil.exe (инструмент для установки)
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: caca946617c681ce6516b7184a9ea506cc67158d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105072"
---
# <a name="installutilexe-installer-tool"></a><span data-ttu-id="99f70-102">Installutil.exe (инструмент для установки)</span><span class="sxs-lookup"><span data-stu-id="99f70-102">Installutil.exe (Installer Tool)</span></span>

<span data-ttu-id="99f70-103">Программа для установки является программой командной строки, с помощью которой можно устанавливать и удалять ресурсы сервера путем выполнения компонентов установщика в соответствующих сборках.</span><span class="sxs-lookup"><span data-stu-id="99f70-103">The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing the installer components in specified assemblies.</span></span> <span data-ttu-id="99f70-104">Эта программа работает совместно с классами в пространстве имен <xref:System.Configuration.Install>.</span><span class="sxs-lookup"><span data-stu-id="99f70-104">This tool works in conjunction with classes in the <xref:System.Configuration.Install> namespace.</span></span>

<span data-ttu-id="99f70-105">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="99f70-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="99f70-106">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="99f70-106">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="99f70-107">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="99f70-107">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="99f70-108">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="99f70-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="99f70-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99f70-109">Syntax</span></span>

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a><span data-ttu-id="99f70-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="99f70-110">Parameters</span></span>

|<span data-ttu-id="99f70-111">Аргумент</span><span class="sxs-lookup"><span data-stu-id="99f70-111">Argument</span></span>|<span data-ttu-id="99f70-112">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="99f70-112">Description</span></span>|
|--------------|-----------------|
|`assembly`|<span data-ttu-id="99f70-113">Имя файла сборки, в которой должны выполняться компоненты установщика.</span><span class="sxs-lookup"><span data-stu-id="99f70-113">The file name of the assembly in which to execute the installer components.</span></span> <span data-ttu-id="99f70-114">Пропустите этот параметр, если указывается строгое имя сборки с помощью параметра `/AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="99f70-114">Omit this parameter if you want to specify the assembly's strong name by using the `/AssemblyName` option.</span></span>|

<a name="options"></a>

## <a name="options"></a><span data-ttu-id="99f70-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="99f70-115">Options</span></span>

|<span data-ttu-id="99f70-116">Параметр</span><span class="sxs-lookup"><span data-stu-id="99f70-116">Option</span></span>|<span data-ttu-id="99f70-117">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="99f70-117">Description</span></span>|
|------------|-----------------|
|`/h[elp]`<br /><br /> <span data-ttu-id="99f70-118">-или-</span><span class="sxs-lookup"><span data-stu-id="99f70-118">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="99f70-119">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="99f70-119">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="99f70-120">`/help` *сборка*</span><span class="sxs-lookup"><span data-stu-id="99f70-120">`/help` *assembly*</span></span><br /><br /> <span data-ttu-id="99f70-121">-или-</span><span class="sxs-lookup"><span data-stu-id="99f70-121">-or-</span></span><br /><br /> <span data-ttu-id="99f70-122">`/?` *сборка*</span><span class="sxs-lookup"><span data-stu-id="99f70-122">`/?` *assembly*</span></span>|<span data-ttu-id="99f70-123">Отображает дополнительные параметры, распознаваемые отдельными установщиками в пределах указанной сборки, вместе с синтаксисом команд и параметров для программы InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-123">Displays additional options recognized by individual installers within the specified assembly, along with command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="99f70-124">Этот параметр добавляет текст, возвращенный каждым свойством компонента установщика <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>, в текст справки программы InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-124">This option adds the text returned by each installer component's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property to the help text of InstallUtil.exe.</span></span>|
|<span data-ttu-id="99f70-125">`/AssemblyName` "*имя_сборки*,</span><span class="sxs-lookup"><span data-stu-id="99f70-125">`/AssemblyName` "*assemblyName*</span></span><br /><br /> <span data-ttu-id="99f70-126">Version = *основная.дополнительная.сборка.редакция*,</span><span class="sxs-lookup"><span data-stu-id="99f70-126">,Version=*major.minor.build.revision*</span></span><br /><br /> <span data-ttu-id="99f70-127">Culture = *языковой стандарт*,</span><span class="sxs-lookup"><span data-stu-id="99f70-127">,Culture=*locale*</span></span><br /><br /> <span data-ttu-id="99f70-128">PublicKeyToken = *publicKeyToken*"</span><span class="sxs-lookup"><span data-stu-id="99f70-128">,PublicKeyToken=*publicKeyToken*"</span></span>|<span data-ttu-id="99f70-129">Задает строгое имя сборки, которое требуется зарегистрировать в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="99f70-129">Specifies the strong name of an assembly, which must be registered in the global assembly cache.</span></span> <span data-ttu-id="99f70-130">Имя сборки должно содержать версию, язык и региональные параметры, а также токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="99f70-130">The assembly name must be fully qualified with the version, culture, and public key token of the assembly.</span></span> <span data-ttu-id="99f70-131">Полное имя должно быть заключено в кавычки.</span><span class="sxs-lookup"><span data-stu-id="99f70-131">The fully qualified name must be surrounded by quotes.</span></span><br /><br /> <span data-ttu-id="99f70-132">Например, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" — это полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="99f70-132">For example, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" is a fully qualified assembly name.</span></span>|
|<span data-ttu-id="99f70-133">`/InstallStateDir=[` *имя_каталога* `]`</span><span class="sxs-lookup"><span data-stu-id="99f70-133">`/InstallStateDir=[` *directoryName* `]`</span></span>|<span data-ttu-id="99f70-134">Задает каталог InstallState-файла, содержащего данные, которые используются для удаления сборки.</span><span class="sxs-lookup"><span data-stu-id="99f70-134">Specifies the directory of the .InstallState file that contains the data used to uninstall the assembly.</span></span> <span data-ttu-id="99f70-135">По умолчанию используется каталог, содержащий сборку.</span><span class="sxs-lookup"><span data-stu-id="99f70-135">The default is the directory that contains the assembly.</span></span>|
|<span data-ttu-id="99f70-136">`/LogFile=`[*имя_файла*]</span><span class="sxs-lookup"><span data-stu-id="99f70-136">`/LogFile=`[*filename*]</span></span>|<span data-ttu-id="99f70-137">Задает имя файла журнала, в который записывается ход установки.</span><span class="sxs-lookup"><span data-stu-id="99f70-137">Specifies the name of the log file where installation progress is recorded.</span></span> <span data-ttu-id="99f70-138">По умолчанию, если параметр `/LogFile` не указан, создается файл журнала с именем *имя_сборки*.InstallLog.</span><span class="sxs-lookup"><span data-stu-id="99f70-138">By default, if the `/LogFile` option is omitted, a log file named *assemblyname*.InstallLog is created.</span></span> <span data-ttu-id="99f70-139">Если параметр *имя_файла* не указан, файл журнала не создается.</span><span class="sxs-lookup"><span data-stu-id="99f70-139">If *filename* is omitted, no log file is generated.</span></span>|
|<span data-ttu-id="99f70-140">`/LogToConsole`={`true`&#124;`false`}</span><span class="sxs-lookup"><span data-stu-id="99f70-140">`/LogToConsole`={`true`&#124;`false`}</span></span>|<span data-ttu-id="99f70-141">Если значение — `true`, выходные данные отображаются на консоли.</span><span class="sxs-lookup"><span data-stu-id="99f70-141">If `true`, displays output to the console.</span></span> <span data-ttu-id="99f70-142">Если значение — `false` (значение по умолчанию), выходные данные на консоль не выводятся.</span><span class="sxs-lookup"><span data-stu-id="99f70-142">If `false` (the default), suppresses output to the console.</span></span>|
|`/ShowCallStack`|<span data-ttu-id="99f70-143">Если в ходе установки возникает исключение, содержимое стека вызовов заносится в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="99f70-143">Outputs the call stack to the log file if an exception occurs at any point during installation.</span></span>|
|<span data-ttu-id="99f70-144">`/u`[`ninstall`]</span><span class="sxs-lookup"><span data-stu-id="99f70-144">`/u`[`ninstall`]</span></span>|<span data-ttu-id="99f70-145">Удаляет указанные сборки.</span><span class="sxs-lookup"><span data-stu-id="99f70-145">Uninstalls the specified assemblies.</span></span> <span data-ttu-id="99f70-146">В отличие от других параметров, `/u` применяется ко всем сборкам независимо от того, где этот параметр указан в командной строке.</span><span class="sxs-lookup"><span data-stu-id="99f70-146">Unlike the other options, `/u` applies to all assemblies regardless of where the option appears on the command line.</span></span>|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a><span data-ttu-id="99f70-147">Дополнительные параметры установщика</span><span class="sxs-lookup"><span data-stu-id="99f70-147">Additional Installer Options</span></span>

<span data-ttu-id="99f70-148">Отдельные установщики, используемые в сборке, кроме перечисленных в разделе [Параметры](#options), могут распознавать и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="99f70-148">Individual installers used within an assembly may recognize options in addition to those listed in the [Options](#options) section.</span></span> <span data-ttu-id="99f70-149">Чтобы узнать об этих параметрах, запустите программу InstallUtil.exe с путями к сборкам в командной строке, а также с параметром `/?` или `/help`.</span><span class="sxs-lookup"><span data-stu-id="99f70-149">To learn about these options, run InstallUtil.exe with the paths of the assemblies on the command line along with the `/?` or `/help` option.</span></span> <span data-ttu-id="99f70-150">Чтобы задать эти параметры, необходимо включить их в командную строку вместе с параметрами, распознаваемыми программой InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-150">To specify these options, you include them on the command line along with the options recognized by InstallUtil.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="99f70-151">Текст справки о параметрах, поддерживаемых отдельными компонентами установщика, возвращается свойством <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="99f70-151">Help text on the options supported by individual installer components is returned by the <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="99f70-152">Отдельные параметры, которые были введены в командной строке, доступны программно из свойства <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="99f70-152">The individual options that have been entered on the command line are accessible programmatically from the <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="99f70-153">Все параметры командной строки записываются в файл журнала установки.</span><span class="sxs-lookup"><span data-stu-id="99f70-153">All options and command-line parameters are written to the installation log file.</span></span> <span data-ttu-id="99f70-154">Однако если используется параметр `/Password`, распознаваемый некоторыми компонентами установщика, сведения о пароле будут заменены восемью звездочками (\*) и не будут отображаться в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="99f70-154">However, if you use the `/Password` parameter, which is recognized by some installer components, the password information will be replaced by eight asterisks (\*) and will not appear in the log file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f70-155">В некоторых случаях передаваемые в установщик параметры могут содержать конфиденциальные или личные сведения, которые по умолчанию записываются в обычный текстовый файл журнала.</span><span class="sxs-lookup"><span data-stu-id="99f70-155">In some cases, parameters passed to the installer may include sensitive or personally identifiable information, which, by default, is written to a plain text log file.</span></span> <span data-ttu-id="99f70-156">Для предотвращения этого поведения можно запретить ведение журнала, указав в командной строке `/LogFile=` (без аргумента *имя_файла*) после программы Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-156">To prevent this behavior, you can suppress the log file by specifying `/LogFile=` (with no *filename* argument) after Installutil.exe on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="99f70-157">Примечания</span><span class="sxs-lookup"><span data-stu-id="99f70-157">Remarks</span></span>

<span data-ttu-id="99f70-158">Приложения .NET Framework состоят из традиционных файлов программ и связанных с ними ресурсов, таких как очереди сообщений, журналы событий и счетчики производительности, которые создаются при развертывании приложения.</span><span class="sxs-lookup"><span data-stu-id="99f70-158">.NET Framework applications consist of traditional program files and associated resources, such as message queues, event logs, and performance counters that must be created when the application is deployed.</span></span> <span data-ttu-id="99f70-159">Компоненты установщика сборки могут использоваться для создания таких ресурсов при установке приложения и для их удаления при удалении приложения.</span><span class="sxs-lookup"><span data-stu-id="99f70-159">You can use an assembly's installer components to create these resources when your application is installed and to remove them when your application is uninstalled.</span></span> <span data-ttu-id="99f70-160">Программа Installutil.exe обнаруживает и выполняет эти компоненты установщика.</span><span class="sxs-lookup"><span data-stu-id="99f70-160">Installutil.exe detects and executes these installer components.</span></span>

<span data-ttu-id="99f70-161">В командной строке можно указать сразу несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="99f70-161">You can specify multiple assemblies on the same command line.</span></span> <span data-ttu-id="99f70-162">Параметры должны указываться перед именами сборок, к установке которых они относятся.</span><span class="sxs-lookup"><span data-stu-id="99f70-162">Any option that occurs before an assembly name applies to that assembly's installation.</span></span> <span data-ttu-id="99f70-163">За исключением `/u` и `/AssemblyName`, параметры являются накопительными, но переопределяемыми.</span><span class="sxs-lookup"><span data-stu-id="99f70-163">Except for `/u` and `/AssemblyName`, options are cumulative but overridable.</span></span> <span data-ttu-id="99f70-164">То есть параметры, указанные для одной сборки, применяются и ко всем последующим сборкам. Исключением являются параметры, с которыми указывается новое значение.</span><span class="sxs-lookup"><span data-stu-id="99f70-164">That is, options specified for one assembly apply to all subsequent assemblies unless the option is specified with a new value.</span></span>

<span data-ttu-id="99f70-165">При запуске программы Installutil.exe для сборки без указания параметров она помещает в каталог сборки следующие три файла.</span><span class="sxs-lookup"><span data-stu-id="99f70-165">If you run Installutil.exe against an assembly without specifying any options, it places the following three files into the assembly's directory:</span></span>

- <span data-ttu-id="99f70-166">InstallUtil.InstallLog — содержит общее описание хода выполнения установки.</span><span class="sxs-lookup"><span data-stu-id="99f70-166">InstallUtil.InstallLog - Contains a general description of the installation progress.</span></span>

- <span data-ttu-id="99f70-167">*имя_сборки*.InstallLog — содержит сведения, относящиеся к этапу фиксации процесса установки.</span><span class="sxs-lookup"><span data-stu-id="99f70-167">*assemblyname*.InstallLog - Contains information specific to the commit phase of the installation process.</span></span> <span data-ttu-id="99f70-168">Дополнительные сведения об этапе фиксации см. в описании метода <xref:System.Configuration.Install.Installer.Commit%2A>.</span><span class="sxs-lookup"><span data-stu-id="99f70-168">For more information about the commit phase, see the <xref:System.Configuration.Install.Installer.Commit%2A> method.</span></span>

- <span data-ttu-id="99f70-169">*имя_сборки*.InstallState — содержит данные, используемые для удаления сборки.</span><span class="sxs-lookup"><span data-stu-id="99f70-169">*assemblyname*.InstallState - Contains data used to uninstall the assembly.</span></span>

<span data-ttu-id="99f70-170">Программа Installutil.exe использует отражение для проверки указанных сборок и поиска всех типов <xref:System.Configuration.Install.Installer>, у которых значение атрибута <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="99f70-170">Installutil.exe uses reflection to inspect the specified assemblies and to find all <xref:System.Configuration.Install.Installer> types that have the <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> attribute set to `true`.</span></span> <span data-ttu-id="99f70-171">Программа, выполняющая метод <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> или <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> для каждого экземпляра типа <xref:System.Configuration.Install.Installer>.</span><span class="sxs-lookup"><span data-stu-id="99f70-171">The tool then executes either the <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> or the <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> method on each instance of the <xref:System.Configuration.Install.Installer> type.</span></span> <span data-ttu-id="99f70-172">Программа Installutil.exe выполняет установку как транзакцию, то есть если какую-либо сборку не удалось установить, отменяется установка всех остальных сборок.</span><span class="sxs-lookup"><span data-stu-id="99f70-172">Installutil.exe performs installation in a transactional manner; that is, if one of the assemblies fails to install, it rolls back the installations of all other assemblies.</span></span> <span data-ttu-id="99f70-173">Удаление не считается транзакцией.</span><span class="sxs-lookup"><span data-stu-id="99f70-173">Uninstall is not transactional.</span></span>

<span data-ttu-id="99f70-174">Программа Installutil.exe не может устанавливать или удалять сборки с отложенной подписью, но может устанавливать и удалять сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="99f70-174">Installutil.exe cannot install or uninstall delay-signed assemblies, but it can install or uninstall strong-named assemblies.</span></span>

<span data-ttu-id="99f70-175">Начиная с .NET Framework версии 2.0, 32-разрядная версия среды CLR поставляется только с 32-разрядной версией программы установщика, однако 64-разрядная версия среды CLR поставляется и с 32-разрядной, и с 64-разрядной версиями программы установщика.</span><span class="sxs-lookup"><span data-stu-id="99f70-175">Starting with the .NET Framework version 2.0, the 32-bit version of the common language runtime (CLR) ships with only the 32-bit version of the Installer tool, but the 64-bit version of the CLR ships with both 32-bit and 64-bit versions of the Installer tool.</span></span> <span data-ttu-id="99f70-176">При работе с 64-разрядной средой CLR используйте 32-разрядную программу установщика для установки 32-разрядных сборок, а 64-разрядную программу установщика — для установки 64-разрядных СIL-сборок.</span><span class="sxs-lookup"><span data-stu-id="99f70-176">When using the 64-bit CLR, use the 32-bit Installer tool to install 32-bit assemblies, and the 64-bit Installer tool to install 64-bit and Microsoft intermediate language (MSIL) assemblies.</span></span> <span data-ttu-id="99f70-177">Обе версии программы установщика ведут себя одинаково.</span><span class="sxs-lookup"><span data-stu-id="99f70-177">Both versions of the Installer tool behave the same.</span></span>

<span data-ttu-id="99f70-178">Программу Installutil.exe невозможно использовать для развертывания службы Windows, написанной на языке C++, потому что программа Installutil.exe не может распознать встроенный машинный код, созданный компилятором C++.</span><span class="sxs-lookup"><span data-stu-id="99f70-178">You cannot use Installutil.exe to deploy a Windows service that was created by using C++, because Installutil.exe cannot recognize the embedded native code that is produced by the C++ compiler.</span></span> <span data-ttu-id="99f70-179">При попытке развернуть службу Windows, написанную на языке C++, с помощью программы Installutil.exe возникает исключение, например <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="99f70-179">If you try to deploy a C++ Windows service with Installutil.exe, an exception such as <xref:System.BadImageFormatException> will be thrown.</span></span> <span data-ttu-id="99f70-180">Для работы с этим сценарием перенесите код службы в модуль C++ и создайте объект установщика на языке C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="99f70-180">To work with this scenario, move the service code to a C++ module, and then write the installer object in C# or Visual Basic.</span></span>

## <a name="examples"></a><span data-ttu-id="99f70-181">Примеры</span><span class="sxs-lookup"><span data-stu-id="99f70-181">Examples</span></span>

<span data-ttu-id="99f70-182">Следующая команда выводит описание синтаксиса и параметров команды для программы InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-182">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span>

```console
installutil /?
```

<span data-ttu-id="99f70-183">Следующая команда выводит описание синтаксиса и параметров команды для программы InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="99f70-183">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="99f70-184">Она также отображает для `myAssembly.exe` описание и список параметров, поддерживаемых компонентами установщика, если свойству <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> установщика было задано значение текста справки.</span><span class="sxs-lookup"><span data-stu-id="99f70-184">It also displays a description and list of options supported by the installer components in `myAssembly.exe` if help text has been assigned to the installer's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span>

```console
installutil /? myAssembly.exe
```

<span data-ttu-id="99f70-185">Следующая команда выполняет компоненты установщика в сборке `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="99f70-185">The following command executes the installer components in the assembly `myAssembly.exe`.</span></span>

```console
installutil myAssembly.exe
```

<span data-ttu-id="99f70-186">Следующая команда выполняет компоненты установщика в сборке с помощью ключа `/AssemblyName` и полного имени.</span><span class="sxs-lookup"><span data-stu-id="99f70-186">The following command executes the installer components in an assembly by using the `/AssemblyName` switch and a fully qualified name.</span></span>

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="99f70-187">Следующая команда выполняет компоненты установщика в сборке, заданной по имени файла, и в сборке, заданной по строгому имени.</span><span class="sxs-lookup"><span data-stu-id="99f70-187">The following command executes the installer components in an assembly specified by file name and in an assembly specified by strong name.</span></span> <span data-ttu-id="99f70-188">Обратите внимание, что все сборки, указанные по имени файла, должны предшествовать сборкам, указанным по строгому имени в командной строке, потому что параметр `/AssemblyName` не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="99f70-188">Note that all assemblies specified by file name must precede assemblies specified by strong name on the command line, because the `/AssemblyName` option cannot be overridden.</span></span>

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="99f70-189">Следующая команда выполняет компоненты программы удаления в сборке `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="99f70-189">The following command executes the uninstaller components in the assembly `myAssembly.exe`.</span></span>

```console
installutil /u myAssembly.exe
```

<span data-ttu-id="99f70-190">Следующая команда выполняет компоненты программы удаления в сборках `myAssembly1.exe` и `myAssembly2.exe`.</span><span class="sxs-lookup"><span data-stu-id="99f70-190">The following command executes the uninstaller components in the assemblies `myAssembly1.exe` and `myAssembly2.exe`.</span></span>

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

<span data-ttu-id="99f70-191">Поскольку позиция параметра `/u` в командной строке не имеет значения, результат аналогичен выполнению следующей команды.</span><span class="sxs-lookup"><span data-stu-id="99f70-191">Because the position of the `/u` option on the command line is not important, this is equivalent to the following command.</span></span>

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

<span data-ttu-id="99f70-192">Следующая команда выполняет компоненты установщика в сборке `myAssembly.exe` и указывает, что сведения о ходе установки должны записываться в файл `myLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="99f70-192">The following command executes the installers in the assembly `myAssembly.exe` and specifies that progress information will be written to `myLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

<span data-ttu-id="99f70-193">Следующая команда запускает установщики в сборке `myAssembly.exe`, указывает, что сведения о ходе выполнения должны записываться в файл `myLog.InstallLog`, и использует настраиваемый параметр установщика `/reg` для указания, что обновления должны вноситься в системный реестр.</span><span class="sxs-lookup"><span data-stu-id="99f70-193">The following command executes the installers in the assembly `myAssembly.exe`, specifies that progress information should be written to `myLog.InstallLog`, and uses the installers' custom `/reg` option to specify that updates should be made to the system registry.</span></span>

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

<span data-ttu-id="99f70-194">Следующая команда запускает установщики в сборке `myAssembly.exe`, использует пользовательский параметр установщика `/email` для указания адреса электронной почты пользователя и не ведет запись в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="99f70-194">The following command executes the installers in the assembly `myAssembly.exe`, uses the installer's custom `/email` option to specify the user's email address, and suppresses output to the log file.</span></span>

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

<span data-ttu-id="99f70-195">Следующая команда записывает сведения о ходе установки для сборки `myAssembly.exe` в журнал `myLog.InstallLog`, а сведения для сборки `myTestAssembly.exe` — в журнал `myTestLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="99f70-195">The following command writes the installation progress for `myAssembly.exe` to `myLog.InstallLog` and writes the progress for `myTestAssembly.exe` to `myTestLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a><span data-ttu-id="99f70-196">См. также</span><span class="sxs-lookup"><span data-stu-id="99f70-196">See also</span></span>

- <xref:System.Configuration.Install>
- [<span data-ttu-id="99f70-197">Инструменты</span><span class="sxs-lookup"><span data-stu-id="99f70-197">Tools</span></span>](index.md)
- [<span data-ttu-id="99f70-198">Командные строки</span><span class="sxs-lookup"><span data-stu-id="99f70-198">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
