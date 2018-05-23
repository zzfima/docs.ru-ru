---
title: Regsvcs.exe (программа установки служб .NET)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a13912d006b522e86997fc7850befb996db4b7bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="2a10a-102">Regsvcs.exe (программа установки служб .NET)</span><span class="sxs-lookup"><span data-stu-id="2a10a-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="2a10a-103">Программа установки служб .NET выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2a10a-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
-   <span data-ttu-id="2a10a-104">Загружает и регистрирует сборку.</span><span class="sxs-lookup"><span data-stu-id="2a10a-104">Loads and registers an assembly.</span></span>  
  
-   <span data-ttu-id="2a10a-105">Создает, регистрирует и устанавливает библиотеку типов в указанное приложение COM+.</span><span class="sxs-lookup"><span data-stu-id="2a10a-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
-   <span data-ttu-id="2a10a-106">Настраивает службы, которые были программно добавлены в создаваемый класс.</span><span class="sxs-lookup"><span data-stu-id="2a10a-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="2a10a-107">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="2a10a-107">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="2a10a-108">Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2a10a-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="2a10a-109">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="2a10a-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a10a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a10a-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a10a-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a10a-111">Parameters</span></span>  
  
|<span data-ttu-id="2a10a-112">Аргумент</span><span class="sxs-lookup"><span data-stu-id="2a10a-112">Argument</span></span>|<span data-ttu-id="2a10a-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a10a-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2a10a-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="2a10a-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="2a10a-115">Исходный файл сборки.</span><span class="sxs-lookup"><span data-stu-id="2a10a-115">The source assembly file.</span></span> <span data-ttu-id="2a10a-116">Сборка должна быть подписана с использованием строгого имени.</span><span class="sxs-lookup"><span data-stu-id="2a10a-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="2a10a-117">Дополнительные сведения см. в разделе [Подпись сборки строгим именем](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="2a10a-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="2a10a-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="2a10a-118">Option</span></span>|<span data-ttu-id="2a10a-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a10a-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2a10a-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="2a10a-120">**/appdir:** *path*</span></span>|<span data-ttu-id="2a10a-121">Определяет корневой каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="2a10a-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="2a10a-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="2a10a-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="2a10a-123">Задает имя приложения COM+, которое следует найти или создать.</span><span class="sxs-lookup"><span data-stu-id="2a10a-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="2a10a-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="2a10a-124">**/c**</span></span>|<span data-ttu-id="2a10a-125">Создает конечное приложение.</span><span class="sxs-lookup"><span data-stu-id="2a10a-125">Creates the target application.</span></span>|  
|<span data-ttu-id="2a10a-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="2a10a-126">**/componly**</span></span>|<span data-ttu-id="2a10a-127">Выполняет только конфигурирование компонентов, методы и интерфейсы игнорируются.</span><span class="sxs-lookup"><span data-stu-id="2a10a-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="2a10a-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="2a10a-128">**/exapp**</span></span>|<span data-ttu-id="2a10a-129">Указывает, что программа будет работать с существующим приложением.</span><span class="sxs-lookup"><span data-stu-id="2a10a-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="2a10a-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="2a10a-130">**/extlb**</span></span>|<span data-ttu-id="2a10a-131">Использует существующую библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="2a10a-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="2a10a-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="2a10a-132">**/fc**</span></span>|<span data-ttu-id="2a10a-133">Находит или создает конечное приложение.</span><span class="sxs-lookup"><span data-stu-id="2a10a-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="2a10a-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="2a10a-134">**/help**</span></span>|<span data-ttu-id="2a10a-135">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="2a10a-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="2a10a-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="2a10a-136">**/noreconfig**</span></span>|<span data-ttu-id="2a10a-137">Запрещает изменять конфигурации существующего конечного приложения.</span><span class="sxs-lookup"><span data-stu-id="2a10a-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="2a10a-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="2a10a-138">**/nologo**</span></span>|<span data-ttu-id="2a10a-139">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="2a10a-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="2a10a-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="2a10a-140">**/parname:** *name*</span></span>|<span data-ttu-id="2a10a-141">Задает имя или идентификатор приложения COM+, которое следует найти или создать.</span><span class="sxs-lookup"><span data-stu-id="2a10a-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="2a10a-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="2a10a-142">**/reconfig**</span></span>|<span data-ttu-id="2a10a-143">Изменяет конфигурацию существующего конечного приложения.</span><span class="sxs-lookup"><span data-stu-id="2a10a-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="2a10a-144">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a10a-144">This is the default.</span></span>|  
|<span data-ttu-id="2a10a-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="2a10a-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="2a10a-146">Задает устанавливаемый файл библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2a10a-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="2a10a-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="2a10a-147">**/u**</span></span>|<span data-ttu-id="2a10a-148">Удаляет конечное приложение.</span><span class="sxs-lookup"><span data-stu-id="2a10a-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="2a10a-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="2a10a-149">**/quiet**</span></span>|<span data-ttu-id="2a10a-150">Задает тихий режим, логотип и сообщения об успешном завершении операций не отображаются.</span><span class="sxs-lookup"><span data-stu-id="2a10a-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="2a10a-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="2a10a-151">**/?**</span></span>|<span data-ttu-id="2a10a-152">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="2a10a-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a10a-153">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a10a-153">Remarks</span></span>  
 <span data-ttu-id="2a10a-154">Программе Regsvcs.exe требуется исходный файл сборки, заданный библиотекой *assemblyFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="2a10a-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="2a10a-155">Эта сборка должна быть подписана с использованием строгого имени.</span><span class="sxs-lookup"><span data-stu-id="2a10a-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="2a10a-156">Дополнительные сведения о подписи с использованием строгого имени см. в разделе [Подпись сборки строгим именем](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="2a10a-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="2a10a-157">Имена конечного приложения и файла библиотеки типов не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="2a10a-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="2a10a-158">Аргумент *applicationName* может быть создан из исходного файла сборки, и в случае его отсутствия он будет создан программой Regsvcs.exe.</span><span class="sxs-lookup"><span data-stu-id="2a10a-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="2a10a-159">Аргумент *typelibraryfile* может задавать имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2a10a-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="2a10a-160">Если имя библиотеки типов не указано, программа Regsvcs.exe по умолчанию использует имя сборки.</span><span class="sxs-lookup"><span data-stu-id="2a10a-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="2a10a-161">Когда программа Regsvcs.exe регистрирует методы компонента, к ней применяются [требования](http://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) и [требования ссылки](../../../docs/framework/misc/link-demands.md) для этих методов.</span><span class="sxs-lookup"><span data-stu-id="2a10a-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](http://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="2a10a-162">Поскольку эта программа выполняется в полностью доверенной среде, большинство требований на получение разрешения удовлетворяется.</span><span class="sxs-lookup"><span data-stu-id="2a10a-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="2a10a-163">Однако программа Regsvcs.exe не может регистрировать компоненты с помощью методов, защищенных требованием или требованием связи для <xref:System.Security.Permissions.StrongNameIdentityPermission> или <xref:System.Security.Permissions.PublisherIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="2a10a-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="2a10a-164">Для работы с программой Regsvcs.exe требуются права администратора на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a10a-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="2a10a-165">Если программа Regsvcs.exe не может выполнить какие-либо из этих действий, на экран выводится соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2a10a-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a10a-166">Примеры</span><span class="sxs-lookup"><span data-stu-id="2a10a-166">Examples</span></span>  
 <span data-ttu-id="2a10a-167">Следующая команда добавляет все открытые классы, содержащиеся в `myTest.dll`, в `myTargetApp` (существующее приложение COM+) и создает библиотеку типов `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="2a10a-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="2a10a-168">Следующая команда добавляет все открытые классы, содержащиеся в `myTest.dll`, в `myTargetApp` (существующее приложение COM+) и создает библиотеку типов `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="2a10a-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a10a-169">См. также</span><span class="sxs-lookup"><span data-stu-id="2a10a-169">See Also</span></span>  
 [<span data-ttu-id="2a10a-170">Инструменты</span><span class="sxs-lookup"><span data-stu-id="2a10a-170">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="2a10a-171">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="2a10a-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="2a10a-172">Командные строки</span><span class="sxs-lookup"><span data-stu-id="2a10a-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
