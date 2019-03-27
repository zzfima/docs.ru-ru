---
title: Практическое руководство. Определение установленных версий платформы .NET Framework
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b7c7704c4f417ef16d3a79fa6d955265e42cf14
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262442"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="dadb6-102">Практическое руководство. Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dadb6-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="dadb6-103">На компьютере можно [установить](https://docs.microsoft.com/dotnet/framework/install) и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="dadb6-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="dadb6-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="dadb6-105">Платформа .NET Framework состоит из двух основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="dadb6-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="dadb6-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="dadb6-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="dadb6-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="dadb6-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="dadb6-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="dadb6-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="dadb6-109">CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="dadb6-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="dadb6-110">В каждой новой версии платформы .NET Framework сохранены функции предыдущих версий и добавлены новые функции.</span><span class="sxs-lookup"><span data-stu-id="dadb6-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="dadb6-111">Можно загружать несколько версий платформы .NET Framework на одном компьютере одновременно. Это значит, что можно установить платформу .NET Framework, не удаляя предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="dadb6-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="dadb6-112">Обычно не рекомендуется удалять предыдущие версии .NET Framework, так как используемое приложение может зависеть от конкретной версии .NET Framework и удаление платформы приведет к сбою в его работе.</span><span class="sxs-lookup"><span data-stu-id="dadb6-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="dadb6-113">Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="dadb6-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="dadb6-114">Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="dadb6-115">Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="dadb6-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="dadb6-116">Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="dadb6-117">Одна версия среды CLR обычно поддерживает несколько версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="dadb6-118">Например, среда CLR версии 4.0.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, а среда CLR версии 4.0.30319.42000 поддерживает .NET Framework начиная с версии 4.6.</span><span class="sxs-lookup"><span data-stu-id="dadb6-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="dadb6-119">Дополнительные сведения о версиях см. в статье [Версии и зависимости платформы .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="dadb6-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="dadb6-120">Получить список версий .NET Framework, установленных на компьютере, можно из реестра.</span><span class="sxs-lookup"><span data-stu-id="dadb6-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="dadb6-121">Вы можете просмотреть реестр в редакторе реестра или отправить запрос с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="dadb6-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="dadb6-122">Поиск .NET Framework 4.5 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="dadb6-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="dadb6-123">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="dadb6-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="dadb6-124">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dadb6-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="dadb6-125">Запрос версий .NET Framework из реестра с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dadb6-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
 - <span data-ttu-id="dadb6-126">Поиск более ранних версий .NET Framework (1–4):</span><span class="sxs-lookup"><span data-stu-id="dadb6-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="dadb6-127">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="dadb6-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="dadb6-128">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dadb6-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="dadb6-129">Получить список версий среды CLR, установленных на компьютере, можно с помощью специального средства или кода.</span><span class="sxs-lookup"><span data-stu-id="dadb6-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
 - [<span data-ttu-id="dadb6-130">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="dadb6-130">Use the Clrver tool</span></span>](#clr_a)  
 - [<span data-ttu-id="dadb6-131">Использование кода для отправки запроса в класс Environment</span><span class="sxs-lookup"><span data-stu-id="dadb6-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="dadb6-132">Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений платформы .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="dadb6-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="dadb6-133">Поиск .NET Framework 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="dadb6-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="dadb6-134">Поиск в реестре .NET Framework версии 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="dadb6-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="dadb6-135">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="dadb6-136">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="dadb6-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="dadb6-137">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="dadb6-138">Если подраздел **Full** отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="dadb6-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dadb6-139">Папка **NET Framework Setup** в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="dadb6-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="dadb6-140">Проверьте значение DWORD с именем **Release**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="dadb6-141">Если оно имеется, платформа .NET Framework 4.5 или более поздней версии установлена.</span><span class="sxs-lookup"><span data-stu-id="dadb6-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="dadb6-142">Это значение является разделом выпуска, который соответствует определенной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="dadb6-143">Например, на приведенном ниже рисунке значение параметра **Release** равно *378389*, что является разделом выпуска для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="dadb6-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="dadb6-144">![Запись реестра для .NET Framework 4.5](media/clr-installdir.png "Запись реестра для .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="dadb6-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="dadb6-145">В приведенной ниже таблице перечислены минимальные значения параметра **Release** для каждой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="dadb6-146">Эти значения можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dadb6-146">You can use these values as follows:</span></span>

- <span data-ttu-id="dadb6-147">Чтобы определить наличие минимальной версии .NET Framework, проверьте, является ли значение **Release** типа DWORD, найденное в реестре, *большим* значения, указанного в таблице, или равным ему.</span><span class="sxs-lookup"><span data-stu-id="dadb6-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="dadb6-148">Например, если приложению требуется .NET Framework 4.7 или более поздней версии, необходимо проверить наличие минимального значения раздела выпуска *460798*.</span><span class="sxs-lookup"><span data-stu-id="dadb6-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="dadb6-149">Чтобы протестировать на наличие нескольких версий, начните с последней версии .NET Framework, а затем протестируйте на каждую последующую более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="dadb6-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="dadb6-150">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dadb6-150">.NET Framework version</span></span>|<span data-ttu-id="dadb6-151">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="dadb6-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="dadb6-152">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="dadb6-152">.NET Framework 4.5</span></span>|<span data-ttu-id="dadb6-153">378389</span><span class="sxs-lookup"><span data-stu-id="dadb6-153">378389</span></span>|
|<span data-ttu-id="dadb6-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="dadb6-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="dadb6-155">378675</span><span class="sxs-lookup"><span data-stu-id="dadb6-155">378675</span></span>|
|<span data-ttu-id="dadb6-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="dadb6-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="dadb6-157">379893</span><span class="sxs-lookup"><span data-stu-id="dadb6-157">379893</span></span>|
|<span data-ttu-id="dadb6-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="dadb6-158">.NET Framework 4.6</span></span>|<span data-ttu-id="dadb6-159">393295</span><span class="sxs-lookup"><span data-stu-id="dadb6-159">393295</span></span>|
|<span data-ttu-id="dadb6-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="dadb6-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="dadb6-161">394254</span><span class="sxs-lookup"><span data-stu-id="dadb6-161">394254</span></span>|
|<span data-ttu-id="dadb6-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="dadb6-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="dadb6-163">394802</span><span class="sxs-lookup"><span data-stu-id="dadb6-163">394802</span></span>|
|<span data-ttu-id="dadb6-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="dadb6-164">.NET Framework 4.7</span></span>|<span data-ttu-id="dadb6-165">460798</span><span class="sxs-lookup"><span data-stu-id="dadb6-165">460798</span></span>|
|<span data-ttu-id="dadb6-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="dadb6-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="dadb6-167">461308</span><span class="sxs-lookup"><span data-stu-id="dadb6-167">461308</span></span>|
|<span data-ttu-id="dadb6-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="dadb6-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="dadb6-169">461808</span><span class="sxs-lookup"><span data-stu-id="dadb6-169">461808</span></span>|

<span data-ttu-id="dadb6-170">Полную таблицу разделов выпуска .NET Framework для определенных версий операционной системы Windows см. в статье [Разделы выпуска .NET Framework и версии операционной системы Windows](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="dadb6-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="dadb6-171">Поиск в реестре .NET Framework 4.5 и более поздних версий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dadb6-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="dadb6-172">Используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="dadb6-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="dadb6-173">Наличие параметра **Release** типа DWORD в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** свидетельствует о том, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dadb6-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="dadb6-174">Проверьте значение параметра **Release**, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="dadb6-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="dadb6-175">Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значению, указанному в [таблице версий .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="dadb6-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="dadb6-176">В следующем примере проверяется значение **Release** в реестре для поиска установленной версии .NET Framework 4.5 или более поздних.</span><span class="sxs-lookup"><span data-stu-id="dadb6-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="dadb6-177">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="dadb6-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="dadb6-178">Проверяется, имеет ли параметр **Release** значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="dadb6-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="dadb6-179">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="dadb6-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="dadb6-180">Проверка наличия минимально необходимой версии .NET Framework (4.5 или более поздней) с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="dadb6-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="dadb6-181">Используйте команды PowerShell для проверки значения параметра **Release** в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="dadb6-182">В приведенных ниже примерах значение **Release** проверяется с целью определить, установлена ли версия 4.6.2 или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dadb6-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="dadb6-183">Код возвращает значение `True`, если одна из таких версий установлена, и `False` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="dadb6-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
```

<span data-ttu-id="dadb6-184">Чтобы проверить наличие другой минимальной необходимой версии .NET Framework, замените значение *394802* в этих примерах на значение **Release** из [таблицы версий NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="dadb6-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="dadb6-185">Поиск более ранних версий .NET Framework (1–4)</span><span class="sxs-lookup"><span data-stu-id="dadb6-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="dadb6-186">Поиск в реестре .NET Framework версий 1–4</span><span class="sxs-lookup"><span data-stu-id="dadb6-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="dadb6-187">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="dadb6-188">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="dadb6-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="dadb6-189">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="dadb6-190">Каждая установленная версия .NET Framework с 1.1 по 3.5 указывается как отдельный подраздел в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="dadb6-191">Пример: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="dadb6-192">Номер версии хранится в параметре **Version** подраздела версии.</span><span class="sxs-lookup"><span data-stu-id="dadb6-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="dadb6-193">Для версии .NET Framework 4 параметр **Version** находится в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** или в обоих этих подразделах.</span><span class="sxs-lookup"><span data-stu-id="dadb6-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dadb6-194">Папка **NET Framework Setup** в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="dadb6-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="dadb6-195">На приведенном ниже рисунке показан подраздел для версии .NET Framework 3.5 вместе с параметром **Version**.</span><span class="sxs-lookup"><span data-stu-id="dadb6-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="dadb6-196">![Запись реестра для .NET Framework 3.5](media/net-4-and-earlier.png ".NET Framework 3.5 и более ранних версий")</span><span class="sxs-lookup"><span data-stu-id="dadb6-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="dadb6-197">Поиск .NET Framework версий 1–4 с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dadb6-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="dadb6-198">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="dadb6-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="dadb6-199">В следующем примере ищутся установленные версии .NET Framework 1–4:</span><span class="sxs-lookup"><span data-stu-id="dadb6-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="dadb6-200">Поиск версий CLR</span><span class="sxs-lookup"><span data-stu-id="dadb6-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="dadb6-201">Поиск текущей версии среды CLR с помощью Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="dadb6-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="dadb6-202">Для определения версий среды CLR, установленных на компьютере, можно использовать [средство CLR Version (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="dadb6-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="dadb6-203">Запустите [Командную строку разработчика для Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) и введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="dadb6-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="dadb6-204">Пример полученных результатов:</span><span class="sxs-lookup"><span data-stu-id="dadb6-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="dadb6-205">Поиск текущей версии среды CLR с помощью класса Environment</span><span class="sxs-lookup"><span data-stu-id="dadb6-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dadb6-206">Для .NET Framework 4.5 и более поздних версий не следует использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dadb6-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="dadb6-207">Вместо этого выполните запрос к реестру, как описано в разделе [Поиск .NET Framework версии 4.5 и более поздних с помощью кода](#net_d).</span><span class="sxs-lookup"><span data-stu-id="dadb6-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="dadb6-208">Выполните запрос к свойству <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="dadb6-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="dadb6-209">Возвращенный объект `System.Version` указывает версию среды выполнения, в которой в настоящее время выполняется код.</span><span class="sxs-lookup"><span data-stu-id="dadb6-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="dadb6-210">Он не содержит версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dadb6-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="dadb6-211">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 возвращаемый объект <xref:System.Version> имеет строковое представление 4.0.30319.*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="dadb6-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="dadb6-212">Для .NET Framework 4.6 и более поздних версий оно имеет форму 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="dadb6-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="dadb6-213">Получив объект `Version`, выполните к нему запрос.</span><span class="sxs-lookup"><span data-stu-id="dadb6-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="dadb6-214">Чтобы получить идентификатор основного выпуска (например, *4* в случае версии 4.0), используйте свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dadb6-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="dadb6-215">Чтобы получить идентификатор дополнительной версии (например, *0* в случае версии 4.0), используйте свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dadb6-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="dadb6-216">Чтобы получить всю строку версии (например, *4.0.30319.18010*), используйте метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dadb6-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="dadb6-217">Он возвращает одно значение, соответствующее версии среды выполнения, в которой выполняется код.</span><span class="sxs-lookup"><span data-stu-id="dadb6-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="dadb6-218">Он не возвращает версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dadb6-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="dadb6-219">В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды CLR:</span><span class="sxs-lookup"><span data-stu-id="dadb6-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="dadb6-220">См. также</span><span class="sxs-lookup"><span data-stu-id="dadb6-220">See also</span></span>

- [<span data-ttu-id="dadb6-221">Практическое руководство. Определение установленных обновлений платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dadb6-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="dadb6-222">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="dadb6-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="dadb6-223">Версии и зависимости платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dadb6-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
