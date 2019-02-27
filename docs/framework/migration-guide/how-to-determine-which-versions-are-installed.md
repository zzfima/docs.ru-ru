---
title: Как выполнить  Определение установленных версий платформы .NET Framework
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584178"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="3edb4-102">Как выполнить  Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3edb4-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="3edb4-103">На компьютере можно установить и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="3edb4-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="3edb4-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="3edb4-105">Учтите, что платформа .NET Framework состоит из основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="3edb4-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="3edb4-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="3edb4-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="3edb4-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="3edb4-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="3edb4-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="3edb4-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="3edb4-109">CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="3edb4-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
<span data-ttu-id="3edb4-110">Чтобы получить точный список версий .NET Framework, установленных на компьютере, можно просмотреть реестр или отправить запрос в реестр с помощью кода:</span><span class="sxs-lookup"><span data-stu-id="3edb4-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="3edb4-111">Поиск в реестре .NET Framework версий 1–4</span><span class="sxs-lookup"><span data-stu-id="3edb4-111">Find .NET Framework versions 1-4 in the registry</span></span>](#net_a)  
 [<span data-ttu-id="3edb4-112">Поиск в реестре .NET Framework 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3edb4-112">Find .NET Framework versions 4.5 and later in the registry)</span></span>](#net_b)  
 [<span data-ttu-id="3edb4-113">Использование кода для отправки запроса в реестр (версии 1–4)</span><span class="sxs-lookup"><span data-stu-id="3edb4-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="3edb4-114">Использование кода для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="3edb4-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="3edb4-115">Использование PowerShell для отправки запроса в реестр (версия 4.5 и более поздние)</span><span class="sxs-lookup"><span data-stu-id="3edb4-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  

 <span data-ttu-id="3edb4-116">Чтобы узнать версию среды CLR, можно использовать специальное средство или код:</span><span class="sxs-lookup"><span data-stu-id="3edb4-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="3edb4-117">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="3edb4-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="3edb4-118">Использование кода для отправки запроса в класс System.Environment</span><span class="sxs-lookup"><span data-stu-id="3edb4-118">Using code to query the System.Environment class</span></span>](#clr_b)  

> [!NOTE]
> <span data-ttu-id="3edb4-119">Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="3edb4-119">There is a difference between the .NET Framework version and the common language runtime (CLR) version.</span></span> <span data-ttu-id="3edb4-120">Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-120">The .NET Framework is versioned based on the set of assemblies that form the .NET Framework Class Library.</span></span> <span data-ttu-id="3edb4-121">Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="3edb4-121">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> <span data-ttu-id="3edb4-122">Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework, где одна версия среды CLR обычно поддерживает несколько версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-122">The CLR is versioned based on the runtime on which .NET Framework applications execute, and a single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="3edb4-123">CLR версии 4.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, а среда CLR версии 4.30319.42000 поддерживает .NET Framework, начиная с версии 4.6.</span><span class="sxs-lookup"><span data-stu-id="3edb4-123">CLR version 4.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2; CLR version 4.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> <span data-ttu-id="3edb4-124">Дополнительные сведения см. в описании свойства <xref:System.Environment.Version?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3edb4-124">For more information, see the <xref:System.Environment.Version?displayProperty=nameWithType> property.</span></span>

 <span data-ttu-id="3edb4-125">Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="3edb4-125">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="3edb4-126">Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="3edb4-126">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a><span data-ttu-id="3edb4-127">Поиск в реестре .NET Framework версий 1–4</span><span class="sxs-lookup"><span data-stu-id="3edb4-127">Find .NET Framework versions 1-4 in the registry</span></span> 
  
1.  <span data-ttu-id="3edb4-128">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3edb4-128">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="3edb4-129">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="3edb4-129">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="3edb4-130">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="3edb4-130">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="3edb4-131">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="3edb4-131">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="3edb4-132">Установленные версии .NET Framework с 1.1 по 3.5 перечислены как подразделы в подразделе `NDP`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-132">For .NET Framework versions 1.1 through 3.5, the installed versions are listed as subkeys under the `NDP` subkey.</span></span> <span data-ttu-id="3edb4-133">Номер версии хранится в записи **Version** подраздела версий.</span><span class="sxs-lookup"><span data-stu-id="3edb4-133">The version number is stored in the version subkey's **Version** entry.</span></span> 
     
     <span data-ttu-id="3edb4-134">Для .NET Framework 4 запись **Version** находится в подразделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` или `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` либо в обоих подразделах.</span><span class="sxs-lookup"><span data-stu-id="3edb4-134">For .NET Framework 4, the **Version** entry is under the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` subkey, the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3edb4-135">Папка NET Framework Setup в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="3edb4-135">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="3edb4-136">На следующем рисунке показан подраздел .NET Framework 3.5 вместе с записью **Version**.</span><span class="sxs-lookup"><span data-stu-id="3edb4-136">The following figure shows that the subkey for the .NET Framework 3.5 along with its **Version** entry.</span></span>

     <span data-ttu-id="3edb4-137">![Запись реестра для .NET Framework 3.5](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 и более ранних версий")</span><span class="sxs-lookup"><span data-stu-id="3edb4-137">![The registry entry for the .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 and earlier versions")</span></span>

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="3edb4-138">Поиск в реестре .NET Framework версии 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3edb4-138">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="3edb4-139">В меню **Пуск** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3edb4-139">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="3edb4-140">В поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="3edb4-140">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="3edb4-141">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="3edb4-141">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="3edb4-142">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="3edb4-142">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="3edb4-143">Обратите внимание, что путь к подразделу `Full` включает подраздел `Net Framework` вместо `.NET Framework`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-143">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3edb4-144">Если подраздел `Full` отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="3edb4-144">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="3edb4-145">Проверьте значение DWORD с именем `Release`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-145">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="3edb4-146">Наличие значения DWORD `Release` указывает, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3edb4-146">The existence of the `Release` DWORD indicates that .NET Framework 4.5 or later has been installed on that computer.</span></span> <span data-ttu-id="3edb4-147">Это значение является разделом выпуска, который соответствует определенной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-147">Its value is a release key that corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="3edb4-148">Например, на следующем рисунке значение параметра DWORD `Release` равно 378389, что является разделом выпуска для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="3edb4-148">In the following figure, for example, the value of the `Release` DWORD is 378389, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="3edb4-149">![Запись реестра для .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="3edb4-149">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

<span data-ttu-id="3edb4-150">В следующей таблице перечислены минимальные значения параметра DWORD `Release` для каждой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-150">The following table lists the minimum value of the `Release` DWORD for each .NET Framework version.</span></span> <span data-ttu-id="3edb4-151">Эти значения можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3edb4-151">You can use these values as follows:</span></span>

- <span data-ttu-id="3edb4-152">Чтобы определить наличие минимальной версии .NET Framework, проверьте, является ли значение DWORD `Release`, найденное в реестре, *большим* значения, указанного в таблице, или равным ему.</span><span class="sxs-lookup"><span data-stu-id="3edb4-152">To determine whether a minimum .NET Framework version is present, test whether the `Release` DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="3edb4-153">Например, если приложению требуется .NET Framework 4.7 или более поздней версии, необходимо проверить на наличие минимального значения раздела выпуска 460798.</span><span class="sxs-lookup"><span data-stu-id="3edb4-153">For example, if your application requires .NET Framework 4.7 or later, you would test for a minimum release key value of 460798.</span></span>

- <span data-ttu-id="3edb4-154">Чтобы протестировать на наличие нескольких версий, начните с последней версии .NET Framework, а затем протестируйте на каждую последующую более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="3edb4-154">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|<span data-ttu-id="3edb4-155">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3edb4-155">.NET Framework Version</span></span>|<span data-ttu-id="3edb4-156">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="3edb4-156">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="3edb4-157">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="3edb4-157">.NET Framework 4.5</span></span>|<span data-ttu-id="3edb4-158">378389</span><span class="sxs-lookup"><span data-stu-id="3edb4-158">378389</span></span>|
|<span data-ttu-id="3edb4-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="3edb4-159">.NET Framework 4.5.1</span></span>|<span data-ttu-id="3edb4-160">378675</span><span class="sxs-lookup"><span data-stu-id="3edb4-160">378675</span></span>|
|<span data-ttu-id="3edb4-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="3edb4-161">.NET Framework 4.5.2</span></span>|<span data-ttu-id="3edb4-162">379893</span><span class="sxs-lookup"><span data-stu-id="3edb4-162">379893</span></span>|
|<span data-ttu-id="3edb4-163">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="3edb4-163">.NET Framework 4.6</span></span>|<span data-ttu-id="3edb4-164">393295</span><span class="sxs-lookup"><span data-stu-id="3edb4-164">393295</span></span>|
|<span data-ttu-id="3edb4-165">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="3edb4-165">.NET Framework 4.6.1</span></span>|<span data-ttu-id="3edb4-166">394254</span><span class="sxs-lookup"><span data-stu-id="3edb4-166">394254</span></span>|
|<span data-ttu-id="3edb4-167">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="3edb4-167">.NET Framework 4.6.2</span></span>|<span data-ttu-id="3edb4-168">394802</span><span class="sxs-lookup"><span data-stu-id="3edb4-168">394802</span></span>|
|<span data-ttu-id="3edb4-169">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="3edb4-169">.NET Framework 4.7</span></span>|<span data-ttu-id="3edb4-170">460798</span><span class="sxs-lookup"><span data-stu-id="3edb4-170">460798</span></span>|
|<span data-ttu-id="3edb4-171">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="3edb4-171">.NET Framework 4.7.1</span></span>|<span data-ttu-id="3edb4-172">461308</span><span class="sxs-lookup"><span data-stu-id="3edb4-172">461308</span></span>|
|<span data-ttu-id="3edb4-173">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="3edb4-173">.NET Framework 4.7.2</span></span>|<span data-ttu-id="3edb4-174">461808</span><span class="sxs-lookup"><span data-stu-id="3edb4-174">461808</span></span>|

<span data-ttu-id="3edb4-175">Полную таблицу разделов выпуска .NET Framework для определенных версий операционной системы Windows см. в статье [Разделы выпуска .NET Framework и версии операционной системы Windows](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="3edb4-175">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a><span data-ttu-id="3edb4-176">Поиск в реестре .NET Framework версий 1–4 с помощью кода</span><span class="sxs-lookup"><span data-stu-id="3edb4-176">Find .NET Framework versions 1-4 with code</span></span>

- <span data-ttu-id="3edb4-177">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, чтобы получить доступ к подразделу `Software\Microsoft\NET Framework Setup\NDP\` в ветви `HKEY_LOCAL_MACHINE` реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="3edb4-177">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the `Software\Microsoft\NET Framework Setup\NDP\` subkey under `HKEY_LOCAL_MACHINE` branch in the Windows registry.</span></span>

     <span data-ttu-id="3edb4-178">В следующем коде показан пример этого запроса.</span><span class="sxs-lookup"><span data-stu-id="3edb4-178">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3edb4-179">Этот код не показывает, как обнаружить .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3edb4-179">This code does not show how to detect .NET Framework 4.5 or later.</span></span> <span data-ttu-id="3edb4-180">Для обнаружения этих версий проверьте DWORD `Release`, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="3edb4-180">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="3edb4-181">Для кода, обнаруживающего .NET Framework 4.5 или более поздние версии, см. следующий раздел в данной статье.</span><span class="sxs-lookup"><span data-stu-id="3edb4-181">For code that detects .NET Framework 4.5 or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="3edb4-182">Поиск в реестре .NET Framework 4.5 и более поздних версий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="3edb4-182">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="3edb4-183">Наличие значения DWORD `Release` в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` указывает на то, что среда .NET Framework 4.5 или более поздней версии установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3edb4-183">The existence of the `Release` DWORD in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key indicates that the .NET Framework 4.5 or later is installed on a computer.</span></span> <span data-ttu-id="3edb4-184">Значение ключевого слова указывает на установленную версию.</span><span class="sxs-lookup"><span data-stu-id="3edb4-184">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="3edb4-185">Чтобы проверить это ключевое слово, используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="3edb4-185">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the subkey in the Windows registry.</span></span>

2. <span data-ttu-id="3edb4-186">Проверьте значение ключевого слова `Release`, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="3edb4-186">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="3edb4-187">Чтобы обеспечить совместимость с будущими версиями, значение должно быть больше или равно значению, указанному в таблице в разделе [Поиск в реестре .NET Framework версии 4.5 и более поздних версии](#net_b).</span><span class="sxs-lookup"><span data-stu-id="3edb4-187">To be forward-compatible, you can check for a value greater than or equal to the value listed in the table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section.</span></span>

<span data-ttu-id="3edb4-188">В следующем примере в реестре проверяется значение `Release`, чтобы определить, установлена ли версия 4.5 или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3edb4-188">The following example checks the `Release` value in the registry to determine whether .NET Framework 4.5 or a later version is installed.</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="3edb4-189">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="3edb4-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="3edb4-190">Проверяется, имеет ли запись `Release` значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="3edb4-190">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="3edb4-191">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="3edb4-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="3edb4-192">Проверка наличия минимально необходимой версии .NET Framework (4.5 и более поздней версии) с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3edb4-192">Check for a minimum required .NET Framework version (4.5 and later) with PowerShell</span></span>

<span data-ttu-id="3edb4-193">В следующем примере проверяется значение ключевого слова `Release`, чтобы определить, установлена ли .NET Framework версии 4.6.2 или выше (`True` или `False`, если нет).</span><span class="sxs-lookup"><span data-stu-id="3edb4-193">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="3edb4-194">Поиск текущей версии среды CLR с помощью Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="3edb4-194">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="3edb4-195">Для определения версий среды CLR, установленных на компьютере, можно использовать инструмент CLR Version (Clrver.exe).</span><span class="sxs-lookup"><span data-stu-id="3edb4-195">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

<span data-ttu-id="3edb4-196">Запустите командную строку разработчика Visual Studio и введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-196">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="3edb4-197">Выходные данные этой команды выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3edb4-197">This command produces output similar to the following:</span></span>

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

<span data-ttu-id="3edb4-198">Дополнительные сведения об использовании этого инструмента см. в разделе [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="3edb4-198">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="3edb4-199">Поиск текущей версии среды CLR с помощью класса Environment</span><span class="sxs-lookup"><span data-stu-id="3edb4-199">Find the current CLR version with the Environment class</span></span>

<span data-ttu-id="3edb4-200">Можно извлечь значение свойства <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>, определяющий версию среды выполнения, в которой в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="3edb4-200">You can retrieve the value of the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="3edb4-201">Это свойство возвращает одно значение, отражающее версию среды выполнения, в которой в данный момент выполняется код. Оно не возвращает версии сборок или другие версии среды выполнения, которые могут быть установлены на компьютере. Можно использовать свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>, чтобы получить идентификатор основного выпуска (например, "4" в случае версии 4.0), свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>, чтобы получить идентификатор дополнительной версии (например, "0" в случае версии 4.0), либо метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>, чтобы получить всю строку версии (например, "4.0.30319.18010", как показано в следующем коде).</span><span class="sxs-lookup"><span data-stu-id="3edb4-201">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> 

<span data-ttu-id="3edb4-202">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> возвращает объект <xref:System.Version>, строковое представление которого имеет форму `4.0.30319.xxxxx`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-202">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="3edb4-203">Для .NET Framework 4.6 и более поздних версий оно имеет форму `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="3edb4-203">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3edb4-204">Для .NET Framework 4.5 и более поздней версии не рекомендуется использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType>, чтобы определить версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3edb4-204">For the .NET Framework 4.5 and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="3edb4-205">Вместо этого рекомендуется отправить запрос в реестр, как описано в разделе [Поиск версий .NET Framework путем отправки запроса в реестр (.NET Framework 4.5 и более поздних версий)](#net_d) выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3edb4-205">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

<span data-ttu-id="3edb4-206">В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="3edb4-206">The following example used the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve runtime version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="3edb4-207">См. также</span><span class="sxs-lookup"><span data-stu-id="3edb4-207">See also</span></span>

- [<span data-ttu-id="3edb4-208">Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3edb4-208">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="3edb4-209">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="3edb4-209">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="3edb4-210">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="3edb4-210">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)
