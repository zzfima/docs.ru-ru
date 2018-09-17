---
title: Практическое руководство. Определение установленных версий платформы .NET Framework
ms.date: 04/10/2018
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
ms.openlocfilehash: 1874d5512f04f22b9c53bdc9e92d0c96e45d21c8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45649501"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="2158b-102">Практическое руководство. Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2158b-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="2158b-103">На компьютере можно установить и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2158b-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="2158b-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="2158b-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="2158b-105">Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="2158b-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="2158b-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="2158b-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="2158b-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="2158b-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="2158b-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="2158b-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="2158b-109">CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="2158b-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="2158b-110">Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:</span><span class="sxs-lookup"><span data-stu-id="2158b-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="2158b-111">Просмотр реестра (версии 1–4)</span><span class="sxs-lookup"><span data-stu-id="2158b-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="2158b-112">Просмотр реестра (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="2158b-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="2158b-113">Использование кода для отправки запроса в реестр (версии 1–4)</span><span class="sxs-lookup"><span data-stu-id="2158b-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="2158b-114">Использование кода для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="2158b-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="2158b-115">Использование PowerShell для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="2158b-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="2158b-116">Чтобы узнать версию среды CLR, можно использовать специальное средство или код:</span><span class="sxs-lookup"><span data-stu-id="2158b-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="2158b-117">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="2158b-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="2158b-118">Использование кода для отправки запроса в класс System.Environment</span><span class="sxs-lookup"><span data-stu-id="2158b-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="2158b-119">Сведения об обнаружении установленных обновлений для каждой версии платформы .NET Framework см. в разделе [Практическое руководство. Определение установленных платформ .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="2158b-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="2158b-120">Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="2158b-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="2158b-121">Поиск версий .NET Framework путем просмотра реестра (.NET Framework 1–4)</span><span class="sxs-lookup"><span data-stu-id="2158b-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="2158b-122">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2158b-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="2158b-123">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="2158b-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="2158b-124">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="2158b-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="2158b-125">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="2158b-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="2158b-126">Установленные версии перечислены в подразделе NDP.</span><span class="sxs-lookup"><span data-stu-id="2158b-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="2158b-127">Номер версии хранится в записи **Version**.</span><span class="sxs-lookup"><span data-stu-id="2158b-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="2158b-128">Для [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] запись **Version** находится в подразделе Client или Full (внутри подраздела NDP) либо в обоих подразделах.</span><span class="sxs-lookup"><span data-stu-id="2158b-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="2158b-129">Папка NET Framework Setup в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="2158b-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="2158b-130">Поиск версий .NET Framework путем просмотра реестра (.NET Framework 4.5 и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="2158b-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="2158b-131">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2158b-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="2158b-132">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="2158b-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="2158b-133">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="2158b-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="2158b-134">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="2158b-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="2158b-135">Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="2158b-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2158b-136">Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="2158b-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="2158b-137">Проверьте значение DWORD с именем `Release`.</span><span class="sxs-lookup"><span data-stu-id="2158b-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="2158b-138">Наличие DWORD `Release` указывает, что на компьютере установлена [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более новая версия.</span><span class="sxs-lookup"><span data-stu-id="2158b-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="2158b-139">![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="2158b-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="2158b-140">Значение DWORD `Release` показывает, какая версия .NET Framework установлена.</span><span class="sxs-lookup"><span data-stu-id="2158b-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="2158b-141">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="2158b-141">Value of the Release DWORD</span></span>|<span data-ttu-id="2158b-142">Версия</span><span class="sxs-lookup"><span data-stu-id="2158b-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="2158b-143">378389</span><span class="sxs-lookup"><span data-stu-id="2158b-143">378389</span></span>|<span data-ttu-id="2158b-144">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="2158b-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="2158b-145">378675</span><span class="sxs-lookup"><span data-stu-id="2158b-145">378675</span></span>|<span data-ttu-id="2158b-146">Платформа .NET Framework 4.5.1, установленная с Windows 8.1 или Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2158b-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="2158b-147">378758</span><span class="sxs-lookup"><span data-stu-id="2158b-147">378758</span></span>|<span data-ttu-id="2158b-148">Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="2158b-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="2158b-149">379893</span><span class="sxs-lookup"><span data-stu-id="2158b-149">379893</span></span>|<span data-ttu-id="2158b-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="2158b-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="2158b-151">Только в системах Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="2158b-151">On Windows 10 systems only: 393295</span></span><br /><br /> <span data-ttu-id="2158b-152">Во всех других версиях ОС: 393297</span><span class="sxs-lookup"><span data-stu-id="2158b-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="2158b-153">Только в системах Windows 10 с ноябрьским обновлением: 394254</span><span class="sxs-lookup"><span data-stu-id="2158b-153">On Windows 10 November Update systems only: 394254</span></span><br /><br /> <span data-ttu-id="2158b-154">Во всех других версиях ОС: 394271</span><span class="sxs-lookup"><span data-stu-id="2158b-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="2158b-155">В юбилейном обновлении Windows 10 и Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="2158b-155">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><br /> <span data-ttu-id="2158b-156">Во всех других версиях ОС: 394806</span><span class="sxs-lookup"><span data-stu-id="2158b-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="2158b-157">Только в обновлении Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="2158b-157">On Windows 10 Creators Update only: 460798</span></span><br/><br/> <span data-ttu-id="2158b-158">Во всех других версиях ОС: 460805</span><span class="sxs-lookup"><span data-stu-id="2158b-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="2158b-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="2158b-159">.NET Framework 4.7</span></span> |
    |<span data-ttu-id="2158b-160">Только в Windows 10 Fall Creators Update: 461308</span><span class="sxs-lookup"><span data-stu-id="2158b-160">On Windows 10 Fall Creators Update only: 461308</span></span><br/><br/> <span data-ttu-id="2158b-161">Во всех других версиях ОС: 461310</span><span class="sxs-lookup"><span data-stu-id="2158b-161">On all other OS versions: 461310</span></span> | <span data-ttu-id="2158b-162">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2158b-162">.NET Framework 4.7.1</span></span> |
    |<span data-ttu-id="2158b-163">Только в обновлении Windows 10 за апрель 2018: 461808</span><span class="sxs-lookup"><span data-stu-id="2158b-163">On Windows 10 April 2018 Update only: 461808</span></span><br/><br/> <span data-ttu-id="2158b-164">Во всех других версиях ОС: 461814</span><span class="sxs-lookup"><span data-stu-id="2158b-164">On all other OS versions: 461814</span></span>| <span data-ttu-id="2158b-165">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2158b-165">.NET Framework 4.7.2</span></span> |
    
<a name="net_c"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="2158b-166">Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 1–4)</span><span class="sxs-lookup"><span data-stu-id="2158b-166">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="2158b-167">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\ в разделе HKEY_LOCAL_MACHINE в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="2158b-167">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="2158b-168">В следующем коде показан пример этого запроса.</span><span class="sxs-lookup"><span data-stu-id="2158b-168">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2158b-169">В этом коде не показано, как обнаружить платформу [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2158b-169">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="2158b-170">Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="2158b-170">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="2158b-171">Для кода, обнаруживающего [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздние версии, см. следующий раздел в данной статье.</span><span class="sxs-lookup"><span data-stu-id="2158b-171">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     <span data-ttu-id="2158b-172">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2158b-172">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="2158b-173">Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)</span><span class="sxs-lookup"><span data-stu-id="2158b-173">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="2158b-174">Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2158b-174">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="2158b-175">Значение ключевого слова указывает на установленную версию.</span><span class="sxs-lookup"><span data-stu-id="2158b-175">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="2158b-176">Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> класса <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу Software\Microsoft\NET Framework Setup\NDP\v4\Full в разделе HKEY_LOCAL_MACHINE реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="2158b-176">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="2158b-177">Проверьте значение ключевого слова `Release`, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="2158b-177">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="2158b-178">Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значениям, указанным в таблице.</span><span class="sxs-lookup"><span data-stu-id="2158b-178">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="2158b-179">Ниже приведен список версий .NET Framework и соответствующих ключевых слов `Release`.</span><span class="sxs-lookup"><span data-stu-id="2158b-179">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="2158b-180">Версия</span><span class="sxs-lookup"><span data-stu-id="2158b-180">Version</span></span>|<span data-ttu-id="2158b-181">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="2158b-181">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="2158b-182">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="2158b-182">.NET Framework 4.5</span></span>|<span data-ttu-id="2158b-183">378389</span><span class="sxs-lookup"><span data-stu-id="2158b-183">378389</span></span>|
    |<span data-ttu-id="2158b-184">Платформа .NET Framework 4.5.1, установленная с Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2158b-184">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="2158b-185">378675</span><span class="sxs-lookup"><span data-stu-id="2158b-185">378675</span></span>|
    |<span data-ttu-id="2158b-186">Платформа .NET Framework 4.5.1, установленная в Windows 8, Windows 7 с пакетом обновления 1 (SP1) или Windows Vista с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="2158b-186">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="2158b-187">378758</span><span class="sxs-lookup"><span data-stu-id="2158b-187">378758</span></span>|
    |<span data-ttu-id="2158b-188">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="2158b-188">.NET Framework 4.5.2</span></span>|<span data-ttu-id="2158b-189">379893</span><span class="sxs-lookup"><span data-stu-id="2158b-189">379893</span></span>|
    |<span data-ttu-id="2158b-190">Платформа .NET Framework 4.6, установленная с Windows 10</span><span class="sxs-lookup"><span data-stu-id="2158b-190">.NET Framework 4.6 installed with Windows 10</span></span>|<span data-ttu-id="2158b-191">393295</span><span class="sxs-lookup"><span data-stu-id="2158b-191">393295</span></span>|
    |<span data-ttu-id="2158b-192">Платформа .NET Framework 4.6, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-192">.NET Framework 4.6 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-193">393297</span><span class="sxs-lookup"><span data-stu-id="2158b-193">393297</span></span>|
    |<span data-ttu-id="2158b-194">Платформа .NET Framework 4.6.1, установленная в Windows 10</span><span class="sxs-lookup"><span data-stu-id="2158b-194">.NET Framework 4.6.1 installed on Windows 10</span></span>|<span data-ttu-id="2158b-195">394254</span><span class="sxs-lookup"><span data-stu-id="2158b-195">394254</span></span>|
    |<span data-ttu-id="2158b-196">Платформа .NET Framework 4.6.1, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-196">.NET Framework 4.6.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-197">394271</span><span class="sxs-lookup"><span data-stu-id="2158b-197">394271</span></span>|
    |<span data-ttu-id="2158b-198">Платформа .NET Framework 4.6.2, установленная в юбилейном обновлении Windows 10 и Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2158b-198">.NET Framework 4.6.2 installed on Windows 10 Anniversary Update and Windows Server 2016</span></span>|<span data-ttu-id="2158b-199">394802</span><span class="sxs-lookup"><span data-stu-id="2158b-199">394802</span></span>|
    |<span data-ttu-id="2158b-200">Платформа .NET Framework 4.6.2, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-200">.NET Framework 4.6.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-201">394806</span><span class="sxs-lookup"><span data-stu-id="2158b-201">394806</span></span>|
    |<span data-ttu-id="2158b-202">.NET Framework 4.7 установлена в обновлении Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="2158b-202">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="2158b-203">460798</span><span class="sxs-lookup"><span data-stu-id="2158b-203">460798</span></span>|
    |<span data-ttu-id="2158b-204">Платформа .NET Framework 4.7, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-204">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-205">460805</span><span class="sxs-lookup"><span data-stu-id="2158b-205">460805</span></span>|
    |<span data-ttu-id="2158b-206">Платформа .NET Framework 4.7.1 установлена в обновлении Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="2158b-206">.NET Framework 4.7.1 installed on Windows 10 Fall Creators Update</span></span>|<span data-ttu-id="2158b-207">461308</span><span class="sxs-lookup"><span data-stu-id="2158b-207">461308</span></span>|
    |<span data-ttu-id="2158b-208">Платформа .NET Framework 4.7.1, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-208">.NET Framework 4.7.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-209">461310</span><span class="sxs-lookup"><span data-stu-id="2158b-209">461310</span></span>|
    |<span data-ttu-id="2158b-210">Платформа .NET Framework 4.7.2, установленная в Windows 10 с обновлением за апрель 2018 г.</span><span class="sxs-lookup"><span data-stu-id="2158b-210">.NET Framework 4.7.2 installed on Windows 10 April 2018 Update</span></span>|<span data-ttu-id="2158b-211">461808</span><span class="sxs-lookup"><span data-stu-id="2158b-211">461808</span></span>|
    |<span data-ttu-id="2158b-212">Платформа .NET Framework 4.7.2, установленная во всех остальных версиях ОС Windows</span><span class="sxs-lookup"><span data-stu-id="2158b-212">.NET Framework 4.7.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="2158b-213">461814</span><span class="sxs-lookup"><span data-stu-id="2158b-213">461814</span></span>|
    
     <span data-ttu-id="2158b-214">В следующем примере проверяется значение `Release` в реестре, чтобы определить, установлена ли [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2158b-214">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     <span data-ttu-id="2158b-215">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="2158b-215">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="2158b-216">Проверяется, имеет ли запись `Release` значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="2158b-216">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="2158b-217">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="2158b-217">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="2158b-218">Проверка минимальной необходимой версии .NET Framework путем запроса к реестру в PowerShell (.NET Framework 4.5 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="2158b-218">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="2158b-219">В приведенном ниже примере проверяется значение ключевого слова `Release` для определения того, установлена ли версия .NET Framework 4.6.2 или более поздняя, вне зависимости от версии Windows (если да, возвращается значение `True`; в противном случае возвращается значение `False`).</span><span class="sxs-lookup"><span data-stu-id="2158b-219">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    <span data-ttu-id="2158b-220">Значение `394802` в предыдущем примере можно заменить на другое значение из приведенной ниже таблицы для проверки наличия другой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2158b-220">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="2158b-221">Версия</span><span class="sxs-lookup"><span data-stu-id="2158b-221">Version</span></span>|<span data-ttu-id="2158b-222">Минимальное значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="2158b-222">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="2158b-223">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="2158b-223">.NET Framework 4.5</span></span>|<span data-ttu-id="2158b-224">378389</span><span class="sxs-lookup"><span data-stu-id="2158b-224">378389</span></span>|
    |<span data-ttu-id="2158b-225">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="2158b-225">.NET Framework 4.5.1</span></span>|<span data-ttu-id="2158b-226">378675</span><span class="sxs-lookup"><span data-stu-id="2158b-226">378675</span></span>|
    |<span data-ttu-id="2158b-227">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="2158b-227">.NET Framework 4.5.2</span></span>|<span data-ttu-id="2158b-228">379893</span><span class="sxs-lookup"><span data-stu-id="2158b-228">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="2158b-229">393295</span><span class="sxs-lookup"><span data-stu-id="2158b-229">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="2158b-230">394254</span><span class="sxs-lookup"><span data-stu-id="2158b-230">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="2158b-231">394802</span><span class="sxs-lookup"><span data-stu-id="2158b-231">394802</span></span>|
    |<span data-ttu-id="2158b-232">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="2158b-232">.NET Framework 4.7</span></span>|<span data-ttu-id="2158b-233">460798</span><span class="sxs-lookup"><span data-stu-id="2158b-233">460798</span></span>|
    |<span data-ttu-id="2158b-234">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2158b-234">.NET Framework 4.7.1</span></span>|<span data-ttu-id="2158b-235">461308</span><span class="sxs-lookup"><span data-stu-id="2158b-235">461308</span></span>|
    |<span data-ttu-id="2158b-236">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2158b-236">.NET Framework 4.7.2</span></span>|<span data-ttu-id="2158b-237">461808</span><span class="sxs-lookup"><span data-stu-id="2158b-237">461808</span></span>|

<a name="clr_a"></a> 
## <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="2158b-238">Поиск текущей версии среды выполнения с помощью средства Clrver</span><span class="sxs-lookup"><span data-stu-id="2158b-238">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="2158b-239">Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version (Clrver.exe).</span><span class="sxs-lookup"><span data-stu-id="2158b-239">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="2158b-240">В командной строке Visual Studio введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="2158b-240">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="2158b-241">Выходные данные этой команды выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2158b-241">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="2158b-242">Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2158b-242">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="2158b-243">Поиск текущей версии среды выполнения путем запроса класса Environment в коде</span><span class="sxs-lookup"><span data-stu-id="2158b-243">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="2158b-244">Запросите извлекаемое свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="2158b-244">Query the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="2158b-245">Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>, чтобы получить идентификатор основного выпуска (например, "4" в случае версии 4,0), свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>, чтобы получить идентификатор дополнительного номера версии (например, "0" в случае версии 4,0), либо метод <xref:System.Object.ToString%2A?displayProperty=nameWithType>, чтобы получить всю строку версии (например, "4.0.30319.18010", как показано в следующем коде).</span><span class="sxs-lookup"><span data-stu-id="2158b-245">You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="2158b-246">Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код; оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2158b-246">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="2158b-247">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="2158b-247">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="2158b-248">Для .NET Framework 4.6 и более поздних версий оно имеет форму `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="2158b-248">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2158b-249">Для [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и более поздней версии не рекомендуется использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2158b-249">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="2158b-250">Вместо этого рекомендуется отправить запрос в реестр, как описано в разделе [Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)](#net_d) выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="2158b-250">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="2158b-251">Ниже приведен пример запроса свойства <xref:System.Environment.Version%2A?displayProperty=nameWithType> для получения сведений о версии среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="2158b-251">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property for runtime version information:</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     <span data-ttu-id="2158b-252">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2158b-252">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="2158b-253">См. также</span><span class="sxs-lookup"><span data-stu-id="2158b-253">See also</span></span>

[<span data-ttu-id="2158b-254">Практическое руководство. Определение установленных обновлений платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2158b-254">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
[<span data-ttu-id="2158b-255">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="2158b-255">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="2158b-256">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="2158b-256">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)  
