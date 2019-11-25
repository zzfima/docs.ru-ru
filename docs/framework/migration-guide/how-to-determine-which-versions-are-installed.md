---
title: Определение установленных версий платформы .NET Framework
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738189"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="8b1d2-102">Практическое руководство. Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b1d2-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="8b1d2-103">На компьютере можно [установить](../install/index.md) и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="8b1d2-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="8b1d2-105">Платформа .NET Framework состоит из двух основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="8b1d2-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="8b1d2-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="8b1d2-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="8b1d2-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="8b1d2-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="8b1d2-109">CLR имеет собственный номер версии (см. статью о [версиях и зависимостях](versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="8b1d2-110">В каждой новой версии платформы .NET Framework сохранены функции предыдущих версий и добавлены новые функции.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="8b1d2-111">Можно загружать несколько версий платформы .NET Framework на одном компьютере одновременно. Это значит, что можно установить платформу .NET Framework, не удаляя предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="8b1d2-112">Обычно не рекомендуется удалять предыдущие версии .NET Framework, так как используемое приложение может зависеть от конкретной версии .NET Framework и удаление платформы приведет к сбою в его работе.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="8b1d2-113">Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="8b1d2-114">Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="8b1d2-115">Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="8b1d2-116">Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="8b1d2-117">Одна версия среды CLR обычно поддерживает несколько версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="8b1d2-118">Например, среда CLR версии 4.0.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, где *xxxxx* меньше 42000, а среда CLR версии 4.0.30319.42000 поддерживает .NET Framework, начиная с версии 4.6.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="8b1d2-119">Дополнительные сведения о версиях см. в статье [Версии и зависимости платформы .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="8b1d2-120">Реестр содержит список версий .NET Framework, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="8b1d2-121">Вы можете просмотреть реестр в редакторе реестра или отправить запрос с помощью кода:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="8b1d2-122">Поиск .NET Framework 4.5 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="8b1d2-123">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="8b1d2-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="8b1d2-124">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="8b1d2-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="8b1d2-125">Запрос версий .NET Framework из реестра с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b1d2-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="8b1d2-126">Поиск более ранних версий .NET Framework (1–4):</span><span class="sxs-lookup"><span data-stu-id="8b1d2-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="8b1d2-127">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="8b1d2-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="8b1d2-128">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="8b1d2-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="8b1d2-129">Получить список версий среды CLR, установленных на компьютере, можно с помощью специального средства или кода.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="8b1d2-130">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="8b1d2-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="8b1d2-131">Использование кода для отправки запроса в класс Environment</span><span class="sxs-lookup"><span data-stu-id="8b1d2-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="8b1d2-132">Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений платформы .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="8b1d2-133">Поиск .NET Framework 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8b1d2-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="8b1d2-134">Для поиска сведений о версии в реестре можно использовать редактор реестра или выполнить запрос к реестру программным способом.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="8b1d2-135">Использование редактора реестра</span><span class="sxs-lookup"><span data-stu-id="8b1d2-135">Use Registry Editor</span></span>

1. <span data-ttu-id="8b1d2-136">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="8b1d2-137">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="8b1d2-138">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="8b1d2-139">Если подраздел **Full** отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b1d2-140">Папка **NET Framework Setup** в реестре *не* начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="8b1d2-141">Проверьте значение DWORD с именем **Release**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="8b1d2-142">Если оно имеется, платформа .NET Framework 4.5 или более поздней версии установлена.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="8b1d2-143">Это значение является разделом выпуска, который соответствует определенной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="8b1d2-144">Например, на приведенном ниже рисунке значение параметра **Release** равно 378389, что является разделом выпуска для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="8b1d2-145">![Запись реестра для .NET Framework 4.5](./media/clr-installdir.png "Запись реестра для .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="8b1d2-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="8b1d2-146">В следующей таблице перечислены значение DWORD **Release** в отдельных операционных системах для .NET Framework 4.5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="8b1d2-147">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b1d2-147">.NET Framework version</span></span>|<span data-ttu-id="8b1d2-148">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="8b1d2-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="8b1d2-149">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="8b1d2-149">.NET Framework 4.5</span></span>|<span data-ttu-id="8b1d2-150">Все версии операционной системы Windows: 378389</span><span class="sxs-lookup"><span data-stu-id="8b1d2-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="8b1d2-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="8b1d2-152">Windows 8.1 и Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="8b1d2-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="8b1d2-153">Все другие версии операционной системы Windows: 378758</span><span class="sxs-lookup"><span data-stu-id="8b1d2-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="8b1d2-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="8b1d2-155">Все версии операционной системы Windows: 379893</span><span class="sxs-lookup"><span data-stu-id="8b1d2-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="8b1d2-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8b1d2-156">.NET Framework 4.6</span></span>|<span data-ttu-id="8b1d2-157">Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="8b1d2-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="8b1d2-158">Все другие версии операционной системы Windows: 393297</span><span class="sxs-lookup"><span data-stu-id="8b1d2-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="8b1d2-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="8b1d2-160">Windows 10 с ноябрьским обновлением: 394254</span><span class="sxs-lookup"><span data-stu-id="8b1d2-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="8b1d2-161">Все остальные версии операционной системы Windows (включая Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="8b1d2-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="8b1d2-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="8b1d2-163">В юбилейном обновлении Windows 10 и Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="8b1d2-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="8b1d2-164">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 394806</span><span class="sxs-lookup"><span data-stu-id="8b1d2-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="8b1d2-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8b1d2-165">.NET Framework 4.7</span></span>|<span data-ttu-id="8b1d2-166">Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="8b1d2-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="8b1d2-167">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 460805</span><span class="sxs-lookup"><span data-stu-id="8b1d2-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="8b1d2-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="8b1d2-169">Windows 10 Fall Creators Update и Windows Server версии 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="8b1d2-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="8b1d2-170">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 461310</span><span class="sxs-lookup"><span data-stu-id="8b1d2-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="8b1d2-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="8b1d2-172">Windows 10 за апрель 2018 г. Update и Windows Server версии 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="8b1d2-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="8b1d2-173">Все остальные операционные системы, кроме Windows 10 с обновлением за апрель 2018 г. и Windows Server версии 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="8b1d2-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="8b1d2-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="8b1d2-174">.NET Framework 4.8</span></span>|<span data-ttu-id="8b1d2-175">Обновление Windows 10 за май 2019 года и обновление Windows 10 за ноябрь 2019 года: 528040</span><span class="sxs-lookup"><span data-stu-id="8b1d2-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="8b1d2-176">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 528049</span><span class="sxs-lookup"><span data-stu-id="8b1d2-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="8b1d2-177">Конкретная версия</span><span class="sxs-lookup"><span data-stu-id="8b1d2-177">Specific version</span></span>

<span data-ttu-id="8b1d2-178">Чтобы определить наличие *конкретной* версии .NET Framework в определенной версии операционной системы Windows, проверьте, *равно* ли значение DWORD **Release** значению, указанному в таблице.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="8b1d2-179">Например, чтобы определить наличие .NET Framework 4.6 в системе Windows 10, проверьте, является ли значение **Release** *равным* 393295.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="8b1d2-180">Минимальная версия</span><span class="sxs-lookup"><span data-stu-id="8b1d2-180">Minimum version</span></span>

<span data-ttu-id="8b1d2-181">Чтобы определить наличие *минимально* необходимой версии .NET Framework, используйте меньшее значение DWORD **RELEASE** для этой версии из предыдущей таблицы.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="8b1d2-182">(Для удобства минимальные значения также перечислены в таблице ниже.)</span><span class="sxs-lookup"><span data-stu-id="8b1d2-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="8b1d2-183">Например, если приложение работает в .NET Framework 4.8 или более поздней версии, проверьте, является ли значение DWORD **RELEASE** *большим или равным* 528040.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="8b1d2-184">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b1d2-184">.NET Framework version</span></span>|<span data-ttu-id="8b1d2-185">Минимальное значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="8b1d2-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="8b1d2-186">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="8b1d2-186">.NET Framework 4.5</span></span>|<span data-ttu-id="8b1d2-187">378389</span><span class="sxs-lookup"><span data-stu-id="8b1d2-187">378389</span></span>|
|<span data-ttu-id="8b1d2-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="8b1d2-189">378675</span><span class="sxs-lookup"><span data-stu-id="8b1d2-189">378675</span></span>|
|<span data-ttu-id="8b1d2-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="8b1d2-191">379893</span><span class="sxs-lookup"><span data-stu-id="8b1d2-191">379893</span></span>|
|<span data-ttu-id="8b1d2-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8b1d2-192">.NET Framework 4.6</span></span>|<span data-ttu-id="8b1d2-193">393295</span><span class="sxs-lookup"><span data-stu-id="8b1d2-193">393295</span></span>|
|<span data-ttu-id="8b1d2-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="8b1d2-195">394254</span><span class="sxs-lookup"><span data-stu-id="8b1d2-195">394254</span></span>|
|<span data-ttu-id="8b1d2-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="8b1d2-197">394802</span><span class="sxs-lookup"><span data-stu-id="8b1d2-197">394802</span></span>|
|<span data-ttu-id="8b1d2-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8b1d2-198">.NET Framework 4.7</span></span>|<span data-ttu-id="8b1d2-199">460798</span><span class="sxs-lookup"><span data-stu-id="8b1d2-199">460798</span></span>|
|<span data-ttu-id="8b1d2-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8b1d2-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="8b1d2-201">461308</span><span class="sxs-lookup"><span data-stu-id="8b1d2-201">461308</span></span>|
|<span data-ttu-id="8b1d2-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="8b1d2-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="8b1d2-203">461808</span><span class="sxs-lookup"><span data-stu-id="8b1d2-203">461808</span></span>|
|<span data-ttu-id="8b1d2-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="8b1d2-204">.NET Framework 4.8</span></span>|<span data-ttu-id="8b1d2-205">528040</span><span class="sxs-lookup"><span data-stu-id="8b1d2-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="8b1d2-206">Несколько версий</span><span class="sxs-lookup"><span data-stu-id="8b1d2-206">Multiple versions</span></span>

<span data-ttu-id="8b1d2-207">Для проверки нескольких версий сначала проверьте значение, которое *больше или равно* наименьшему значению DWORD для новейшей версии .NET Framework, а затем сравните значение с наименьшим значением DWORD для каждой последующей более новой версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="8b1d2-208">Например, если приложению требуется .NET Framework 4.7 или более поздней версии и необходимо определит наличие конкретной версии .NET Framework, сначала проверьте, что значение DWORD **RELEASE** *больше или равно* 461808 (наименьшему значению DWORD для .NET Framework 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="8b1d2-209">Сравните значение DWORD **RELEASE** с наименьшим значением для каждой более поздней версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="8b1d2-210">Отправка запросов в реестр с помощью кода</span><span class="sxs-lookup"><span data-stu-id="8b1d2-210">Query the registry using code</span></span>

1. <span data-ttu-id="8b1d2-211">Используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="8b1d2-212">Наличие параметра **Release** типа DWORD в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** свидетельствует о том, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="8b1d2-213">Проверьте значение параметра **Release**, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="8b1d2-214">Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значению, указанному в [таблице версий .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="8b1d2-215">В следующем примере проверяется значение **Release** в реестре для поиска установленной версии .NET Framework 4.5 или более поздних.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="8b1d2-216">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="8b1d2-217">Проверяется, имеет ли параметр **Release** значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="8b1d2-218">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="8b1d2-219">Использование PowerShell для проверки минимальной требуемой версии</span><span class="sxs-lookup"><span data-stu-id="8b1d2-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="8b1d2-220">Используйте команды PowerShell для проверки значения параметра **Release** в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="8b1d2-221">В приведенных ниже примерах значение **Release** проверяется с целью определить, установлена ли версия 4.6.2 или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="8b1d2-222">Код возвращает значение `True`, если одна из таких версий установлена, и `False` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="8b1d2-223">Чтобы проверить наличие другой минимальной необходимой версии .NET Framework, замените значение `394802` в этих примерах на значение из [таблицы версий .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="8b1d2-224">Используйте наименьшее значение, показанное для этой версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="8b1d2-225">Поиск более ранних версий .NET Framework (1–4)</span><span class="sxs-lookup"><span data-stu-id="8b1d2-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="8b1d2-226">Использование редактора реестра (более ранние версии платформы)</span><span class="sxs-lookup"><span data-stu-id="8b1d2-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="8b1d2-227">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="8b1d2-228">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="8b1d2-229">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="8b1d2-230">Каждая установленная версия .NET Framework с 1.1 по 3.5 указывается как отдельный подраздел в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="8b1d2-231">Пример: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="8b1d2-232">Номер версии хранится в параметре **Version** подраздела версии.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="8b1d2-233">Для версии .NET Framework 4 параметр **Version** находится в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** или в обоих этих подразделах.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b1d2-234">Папка **NET Framework Setup** в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="8b1d2-235">На приведенном ниже рисунке показан подраздел для версии .NET Framework 3.5 вместе с параметром **Version**.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="8b1d2-236">![Запись реестра для .NET Framework 3.5.](./media/net-4-and-earlier.png "NET Framework 3.5 и предыдущие версии")</span><span class="sxs-lookup"><span data-stu-id="8b1d2-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="8b1d2-237">Запрос реестра с помощью кода (более ранние версии платформы)</span><span class="sxs-lookup"><span data-stu-id="8b1d2-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="8b1d2-238">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="8b1d2-239">В следующем примере ищутся установленные версии .NET Framework 1–4:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="8b1d2-240">Поиск версий CLR</span><span class="sxs-lookup"><span data-stu-id="8b1d2-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="8b1d2-241">Использование Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="8b1d2-241">Use Clrver.exe</span></span>

<span data-ttu-id="8b1d2-242">Для определения версий среды CLR, установленных на компьютере, можно использовать [средство CLR Version (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="8b1d2-243">Запустите [Командную строку разработчика для Visual Studio](../tools/developer-command-prompt-for-vs.md) и введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="8b1d2-244">Пример результатов выполнения:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="8b1d2-245">Использование класса Environment</span><span class="sxs-lookup"><span data-stu-id="8b1d2-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b1d2-246">Для .NET Framework 4.5 и более поздних версий не следует использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="8b1d2-247">Вместо этого выполните запрос к реестру, как описано в разделе [Поиск .NET Framework версии 4.5 и более поздних с помощью кода](#net_d).</span><span class="sxs-lookup"><span data-stu-id="8b1d2-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="8b1d2-248">Выполните запрос к свойству <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="8b1d2-249">Возвращенный объект `System.Version` указывает версию среды выполнения, в которой в настоящее время выполняется код.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="8b1d2-250">Он не содержит версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="8b1d2-251">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 возвращаемый объект <xref:System.Version> имеет строковое представление 4.0.30319.*xxxxx*, где *xxxxx* меньше 42000.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="8b1d2-252">Для .NET Framework 4.6 и более поздних версий оно имеет форму 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="8b1d2-253">Получив объект `Version`, выполните к нему запрос.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="8b1d2-254">Чтобы получить идентификатор основного выпуска (например, *4* в случае версии 4.0), используйте свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="8b1d2-255">Чтобы получить идентификатор дополнительной версии (например, *0* в случае версии 4.0), используйте свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="8b1d2-256">Чтобы получить всю строку версии (например, *4.0.30319.18010*), используйте метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8b1d2-257">Он возвращает одно значение, соответствующее версии среды выполнения, в которой выполняется код.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="8b1d2-258">Он не возвращает версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8b1d2-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="8b1d2-259">В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды CLR:</span><span class="sxs-lookup"><span data-stu-id="8b1d2-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="8b1d2-260">См. также</span><span class="sxs-lookup"><span data-stu-id="8b1d2-260">See also</span></span>

- [<span data-ttu-id="8b1d2-261">Практическое руководство. Определение установленных обновлений платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b1d2-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="8b1d2-262">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="8b1d2-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="8b1d2-263">Версии и зависимости платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b1d2-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
