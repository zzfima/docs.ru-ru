---
title: "Практическое руководство. Определение установленных версий платформы .NET Framework"
ms.date: 08/09/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
caps.latest.revision: 62
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: afb01fd47ed2ce3b9c5838f3a8f61c8d34147378
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="f3e99-102">Практическое руководство.Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3e99-102">How to: Determine Which .NET Framework Versions Are Installed</span></span>
<span data-ttu-id="f3e99-103">На компьютере можно установить и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3e99-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="f3e99-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3e99-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="f3e99-105">Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="f3e99-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="f3e99-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="f3e99-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="f3e99-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="f3e99-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="f3e99-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="f3e99-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="f3e99-109">CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="f3e99-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="f3e99-110">Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:</span><span class="sxs-lookup"><span data-stu-id="f3e99-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="f3e99-111">Просмотр реестра (версии 1–4)</span><span class="sxs-lookup"><span data-stu-id="f3e99-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="f3e99-112">Просмотр реестра (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="f3e99-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="f3e99-113">Использование кода для отправки запроса в реестр (версии 1–4)</span><span class="sxs-lookup"><span data-stu-id="f3e99-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="f3e99-114">Использование кода для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="f3e99-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="f3e99-115">Использование PowerShell для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="f3e99-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="f3e99-116">Чтобы узнать версию среды CLR, можно использовать специальное средство или код:</span><span class="sxs-lookup"><span data-stu-id="f3e99-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="f3e99-117">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="f3e99-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="f3e99-118">Использование кода для отправки запроса в класс System.Environment</span><span class="sxs-lookup"><span data-stu-id="f3e99-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="f3e99-119">Сведения об обнаружении установленных обновлений для каждой версии платформы .NET Framework см. в разделе [Практическое руководство. Определение установленных платформ .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="f3e99-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="f3e99-120">Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="f3e99-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="f3e99-121">Поиск версий .NET Framework путем просмотра реестра (.NET Framework 1–4)</span><span class="sxs-lookup"><span data-stu-id="f3e99-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="f3e99-122">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3e99-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="f3e99-123">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="f3e99-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="f3e99-124">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f3e99-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="f3e99-125">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="f3e99-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="f3e99-126">Установленные версии перечислены в подразделе NDP.</span><span class="sxs-lookup"><span data-stu-id="f3e99-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="f3e99-127">Номер версии хранится в записи **Version**.</span><span class="sxs-lookup"><span data-stu-id="f3e99-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="f3e99-128">Для [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] запись **Version** находится в подразделе Client или Full (внутри подраздела NDP) либо в обоих подразделах.</span><span class="sxs-lookup"><span data-stu-id="f3e99-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="f3e99-129">Папка NET Framework Setup в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="f3e99-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
#### <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="f3e99-130">Поиск версий .NET Framework путем просмотра реестра (.NET Framework 4.5 и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="f3e99-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="f3e99-131">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3e99-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="f3e99-132">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="f3e99-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="f3e99-133">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f3e99-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="f3e99-134">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="f3e99-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="f3e99-135">Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3e99-136">Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="f3e99-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="f3e99-137">Проверьте значение DWORD с именем `Release`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="f3e99-138">Наличие DWORD `Release` указывает, что на компьютере установлена [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более новая версия.</span><span class="sxs-lookup"><span data-stu-id="f3e99-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="f3e99-139">![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="f3e99-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="f3e99-140">Значение DWORD `Release` показывает, какая версия .NET Framework установлена.</span><span class="sxs-lookup"><span data-stu-id="f3e99-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    |<span data-ttu-id="f3e99-141">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="f3e99-141">Value of the Release DWORD</span></span>|<span data-ttu-id="f3e99-142">Версия</span><span class="sxs-lookup"><span data-stu-id="f3e99-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="f3e99-143">378389</span><span class="sxs-lookup"><span data-stu-id="f3e99-143">378389</span></span>|<span data-ttu-id="f3e99-144">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="f3e99-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="f3e99-145">378675</span><span class="sxs-lookup"><span data-stu-id="f3e99-145">378675</span></span>|<span data-ttu-id="f3e99-146">Платформа .NET Framework 4.5.1, установленная с Windows 8.1 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f3e99-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="f3e99-147">378758</span><span class="sxs-lookup"><span data-stu-id="f3e99-147">378758</span></span>|<span data-ttu-id="f3e99-148">Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="f3e99-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="f3e99-149">379893</span><span class="sxs-lookup"><span data-stu-id="f3e99-149">379893</span></span>|<span data-ttu-id="f3e99-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f3e99-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="f3e99-151">В системах Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="f3e99-151">On Windows 10 systems: 393295</span></span><br /><br /> <span data-ttu-id="f3e99-152">Во всех других версиях ОС: 393297</span><span class="sxs-lookup"><span data-stu-id="f3e99-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="f3e99-153">В системах Windows 10 с ноябрьским обновлением: 394254</span><span class="sxs-lookup"><span data-stu-id="f3e99-153">On Windows 10 November Update systems: 394254</span></span><br /><br /> <span data-ttu-id="f3e99-154">Во всех других версиях ОС: 394271</span><span class="sxs-lookup"><span data-stu-id="f3e99-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="f3e99-155">В юбилейном обновлении Windows 10 Anniversary Update: 394802</span><span class="sxs-lookup"><span data-stu-id="f3e99-155">On Windows 10 Anniversary Update: 394802</span></span><br /><br /> <span data-ttu-id="f3e99-156">Во всех других версиях ОС: 394806</span><span class="sxs-lookup"><span data-stu-id="f3e99-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="f3e99-157">В обновлении Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="f3e99-157">On Windows 10 Creators Update: 460798</span></span><br/><br/> <span data-ttu-id="f3e99-158">Во всех других версиях ОС: 460805</span><span class="sxs-lookup"><span data-stu-id="f3e99-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="f3e99-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f3e99-159">.NET Framework 4.7</span></span> |

<a name="net_c"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="f3e99-160">Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 1–4)</span><span class="sxs-lookup"><span data-stu-id="f3e99-160">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="f3e99-161">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\ в разделе HKEY_LOCAL_MACHINE в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="f3e99-161">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="f3e99-162">В следующем коде показан пример этого запроса.</span><span class="sxs-lookup"><span data-stu-id="f3e99-162">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3e99-163">В этом коде не показано, как обнаружить платформу [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f3e99-163">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="f3e99-164">Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="f3e99-164">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="f3e99-165">Для кода, обнаруживающего [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздние версии, см. следующий раздел в данной статье.</span><span class="sxs-lookup"><span data-stu-id="f3e99-165">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     <span data-ttu-id="f3e99-166">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3e99-166">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]</span></span>

     <span data-ttu-id="f3e99-167">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3e99-167">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
#### <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="f3e99-168">Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="f3e99-168">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="f3e99-169">Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f3e99-169">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="f3e99-170">Значение ключевого слова указывает на установленную версию.</span><span class="sxs-lookup"><span data-stu-id="f3e99-170">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="f3e99-171">Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> класса <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\v4\Full в разделе HKEY_LOCAL_MACHINE реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="f3e99-171">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=fullName> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="f3e99-172">Проверьте значение ключевого слова `Release`, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="f3e99-172">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="f3e99-173">Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значениям, указанным в таблице.</span><span class="sxs-lookup"><span data-stu-id="f3e99-173">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="f3e99-174">Ниже приведен список версий .NET Framework и соответствующих ключевых слов `Release`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-174">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    |<span data-ttu-id="f3e99-175">Версия</span><span class="sxs-lookup"><span data-stu-id="f3e99-175">Version</span></span>|<span data-ttu-id="f3e99-176">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="f3e99-176">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="f3e99-177">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="f3e99-177">.NET Framework 4.5</span></span>|<span data-ttu-id="f3e99-178">378389</span><span class="sxs-lookup"><span data-stu-id="f3e99-178">378389</span></span>|
    |<span data-ttu-id="f3e99-179">Платформа .NET Framework 4.5.1, установленная с Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f3e99-179">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="f3e99-180">378675</span><span class="sxs-lookup"><span data-stu-id="f3e99-180">378675</span></span>|
    |<span data-ttu-id="f3e99-181">Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="f3e99-181">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="f3e99-182">378758</span><span class="sxs-lookup"><span data-stu-id="f3e99-182">378758</span></span>|
    |<span data-ttu-id="f3e99-183">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f3e99-183">.NET Framework 4.5.2</span></span>|<span data-ttu-id="f3e99-184">379893</span><span class="sxs-lookup"><span data-stu-id="f3e99-184">379893</span></span>|
    |<span data-ttu-id="f3e99-185">Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная с Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3e99-185">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installed with Windows 10</span></span>|<span data-ttu-id="f3e99-186">393295</span><span class="sxs-lookup"><span data-stu-id="f3e99-186">393295</span></span>|
    |<span data-ttu-id="f3e99-187">Платформа [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="f3e99-187">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installed on all other Windows OS versions</span></span>|<span data-ttu-id="f3e99-188">393297</span><span class="sxs-lookup"><span data-stu-id="f3e99-188">393297</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<span data-ttu-id="f3e99-189"> установлена в Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3e99-189"> installed on Windows 10</span></span>|<span data-ttu-id="f3e99-190">394254</span><span class="sxs-lookup"><span data-stu-id="f3e99-190">394254</span></span>|
    |<span data-ttu-id="f3e99-191">Платформа [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="f3e99-191">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] installed on all other Windows OS versions</span></span>|<span data-ttu-id="f3e99-192">394271</span><span class="sxs-lookup"><span data-stu-id="f3e99-192">394271</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<span data-ttu-id="f3e99-193"> установлена в юбилейном обновлении Windows 10 Anniversary Update</span><span class="sxs-lookup"><span data-stu-id="f3e99-193"> installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="f3e99-194">394802</span><span class="sxs-lookup"><span data-stu-id="f3e99-194">394802</span></span>|
    |<span data-ttu-id="f3e99-195">Платформа [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="f3e99-195">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] installed on all other Windows OS versions</span></span>|<span data-ttu-id="f3e99-196">394806</span><span class="sxs-lookup"><span data-stu-id="f3e99-196">394806</span></span>|
    |<span data-ttu-id="f3e99-197">.NET Framework 4.7 установлена в обновлении Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="f3e99-197">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="f3e99-198">460798</span><span class="sxs-lookup"><span data-stu-id="f3e99-198">460798</span></span>|
    |<span data-ttu-id="f3e99-199">Платформа .NET Framework 4.7, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="f3e99-199">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="f3e99-200">460805</span><span class="sxs-lookup"><span data-stu-id="f3e99-200">460805</span></span>|

     <span data-ttu-id="f3e99-201">В следующем примере проверяется значение `Release` в реестре, чтобы определить, установлена ли [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3e99-201">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     <span data-ttu-id="f3e99-202">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3e99-202">[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]   [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]</span></span>

     <span data-ttu-id="f3e99-203">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="f3e99-203">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="f3e99-204">Проверяется, имеет ли запись `Release` значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="f3e99-204">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="f3e99-205">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="f3e99-205">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
#### <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="f3e99-206">Проверка минимальной необходимой версии .NET Framework путем запроса к реестру в PowerShell (.NET Framework 4.5 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="f3e99-206">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="f3e99-207">В приведенном ниже примере проверяется значение ключевого слова `Release` для определения того, установлена ли версия .NET Framework 4.6.2 или более поздняя, вне зависимости от версии Windows (если да, возвращается значение `True`; в противном случае возвращается значение `False`).</span><span class="sxs-lookup"><span data-stu-id="f3e99-207">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    Get-ChildItem "hklm:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | % { $_ -ge 394802 } 
    ```

    <span data-ttu-id="f3e99-208">Значение `394802` в предыдущем примере можно заменить на другое значение из приведенной ниже таблицы для проверки наличия другой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3e99-208">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="f3e99-209">Версия</span><span class="sxs-lookup"><span data-stu-id="f3e99-209">Version</span></span>|<span data-ttu-id="f3e99-210">Минимальное значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="f3e99-210">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="f3e99-211">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f3e99-211">.NET Framework 4.5</span></span>|<span data-ttu-id="f3e99-212">378389</span><span class="sxs-lookup"><span data-stu-id="f3e99-212">378389</span></span>|
    |<span data-ttu-id="f3e99-213">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f3e99-213">.NET Framework 4.5.1</span></span>|<span data-ttu-id="f3e99-214">378675</span><span class="sxs-lookup"><span data-stu-id="f3e99-214">378675</span></span>|
    |<span data-ttu-id="f3e99-215">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f3e99-215">.NET Framework 4.5.2</span></span>|<span data-ttu-id="f3e99-216">379893</span><span class="sxs-lookup"><span data-stu-id="f3e99-216">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="f3e99-217">393295</span><span class="sxs-lookup"><span data-stu-id="f3e99-217">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="f3e99-218">394254</span><span class="sxs-lookup"><span data-stu-id="f3e99-218">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="f3e99-219">394802</span><span class="sxs-lookup"><span data-stu-id="f3e99-219">394802</span></span>|
    |<span data-ttu-id="f3e99-220">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f3e99-220">.NET Framework 4.7</span></span>|<span data-ttu-id="f3e99-221">460798</span><span class="sxs-lookup"><span data-stu-id="f3e99-221">460798</span></span>|

<a name="clr_a"></a> 
#### <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="f3e99-222">Поиск текущей версии среды выполнения с помощью средства Clrver</span><span class="sxs-lookup"><span data-stu-id="f3e99-222">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="f3e99-223">Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version (Clrver.exe).</span><span class="sxs-lookup"><span data-stu-id="f3e99-223">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="f3e99-224">В командной строке Visual Studio введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-224">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="f3e99-225">Выходные данные этой команды выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3e99-225">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="f3e99-226">Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f3e99-226">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
#### <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="f3e99-227">Поиск текущей версии среды выполнения путем запроса класса Environment в коде</span><span class="sxs-lookup"><span data-stu-id="f3e99-227">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="f3e99-228">Запросите извлекаемое свойство <xref:System.Environment.Version%2A?displayProperty=fullName>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="f3e99-228">Query the <xref:System.Environment.Version%2A?displayProperty=fullName> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="f3e99-229">Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=fullName>, чтобы получить идентификатор основного выпуска (например, "4" в случае версии 4,0), свойство <xref:System.Version.Minor%2A?displayProperty=fullName>, чтобы получить идентификатор дополнительного номера версии (например, "0" в случае версии 4,0), либо метод <xref:System.Object.ToString%2A?displayProperty=fullName>, чтобы получить всю строку версии (например, "4.0.30319.18010", как показано в следующем коде).</span><span class="sxs-lookup"><span data-stu-id="f3e99-229">You can use the <xref:System.Version.Major%2A?displayProperty=fullName> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=fullName> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=fullName> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="f3e99-230">Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код; оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f3e99-230">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="f3e99-231">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=fullName> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-231">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=fullName> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="f3e99-232">Для .NET Framework 4.6 и более поздних версий оно имеет форму `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="f3e99-232">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3e99-233">Для [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздней версии не рекомендуется использовать свойство <xref:System.Environment.Version%2A?displayProperty=fullName> для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3e99-233">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=fullName> property to detect the version of the runtime.</span></span> <span data-ttu-id="f3e99-234">Вместо этого рекомендуется отправить запрос в реестр, как описано в разделе [Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)](#net_d) выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f3e99-234">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="f3e99-235">Ниже приведен пример запроса свойства <xref:System.Environment.Version%2A?displayProperty=fullName> для получения сведений о версии среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="f3e99-235">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=fullName> property for runtime version information:</span></span>

     <span data-ttu-id="f3e99-236">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3e99-236">[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]    [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]</span></span>

     <span data-ttu-id="f3e99-237">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3e99-237">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="f3e99-238">См. также</span><span class="sxs-lookup"><span data-stu-id="f3e99-238">See Also</span></span>
 <span data-ttu-id="f3e99-239">[Практическое руководство. Определение установленных обновлений платформы .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="f3e99-239">[How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md) </span></span>  
 <span data-ttu-id="f3e99-240">[Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="f3e99-240">[Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) </span></span>  
 [<span data-ttu-id="f3e99-241">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="f3e99-241">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)

