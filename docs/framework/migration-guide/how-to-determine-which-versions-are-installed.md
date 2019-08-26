---
title: Практическое руководство. Определение установленных версий платформы .NET Framework
ms.date: 04/18/2019
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
ms.openlocfilehash: 5ead6db2c3df3662c4d689bd6ac2466c99b02a15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968262"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="f9d71-102">Практическое руководство. Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9d71-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="f9d71-103">На компьютере можно [установить](https://docs.microsoft.com/dotnet/framework/install) и запустить несколько версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="f9d71-104">При разработке или развертывании приложения могут потребоваться сведения о том, какие версии .NET Framework установлены на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9d71-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="f9d71-105">Платформа .NET Framework состоит из двух основных компонентов, версии которым присваиваются отдельно:</span><span class="sxs-lookup"><span data-stu-id="f9d71-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="f9d71-106">набор сборок, которые являются коллекциями типов и ресурсов, обеспечивающих функции приложений</span><span class="sxs-lookup"><span data-stu-id="f9d71-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="f9d71-107">(.NET Framework и сборкам назначается один номер версии);</span><span class="sxs-lookup"><span data-stu-id="f9d71-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="f9d71-108">среда CLR, которая выполняет код приложения и управляет им.</span><span class="sxs-lookup"><span data-stu-id="f9d71-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="f9d71-109">CLR имеет собственный номер версии (см. раздел [Версии и зависимости .NET Framework](versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="f9d71-109">The CLR is identified by its own version number (see [Versions and Dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="f9d71-110">В каждой новой версии платформы .NET Framework сохранены функции предыдущих версий и добавлены новые функции.</span><span class="sxs-lookup"><span data-stu-id="f9d71-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="f9d71-111">Можно загружать несколько версий платформы .NET Framework на одном компьютере одновременно. Это значит, что можно установить платформу .NET Framework, не удаляя предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="f9d71-112">Обычно не рекомендуется удалять предыдущие версии .NET Framework, так как используемое приложение может зависеть от конкретной версии .NET Framework и удаление платформы приведет к сбою в его работе.</span><span class="sxs-lookup"><span data-stu-id="f9d71-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="f9d71-113">Существует разница между версией .NET Framework и версией общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="f9d71-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
> - <span data-ttu-id="f9d71-114">Версия .NET Framework зависит от набора сборок, которые образуют библиотеку классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="f9d71-115">Например, версии .NET Framework включают в себя 4.5, 4.6.1 и 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="f9d71-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
>- <span data-ttu-id="f9d71-116">Версия среды CLR зависит от среды выполнения, в которой выполняются приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="f9d71-117">Одна версия среды CLR обычно поддерживает несколько версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="f9d71-118">Например, среда CLR версии 4.0.30319.*xxxxx* поддерживает .NET Framework версии с 4 по 4.5.2, где *xxxxx* меньше 42000, а среда CLR версии 4.0.30319.42000 поддерживает .NET Framework, начиная с версии 4.6.</span><span class="sxs-lookup"><span data-stu-id="f9d71-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="f9d71-119">Дополнительные сведения о версиях см. в статье [Версии и зависимости платформы .NET Framework](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f9d71-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="f9d71-120">Получить список версий .NET Framework, установленных на компьютере, можно из реестра.</span><span class="sxs-lookup"><span data-stu-id="f9d71-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="f9d71-121">Вы можете просмотреть реестр в редакторе реестра или отправить запрос с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="f9d71-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>

- <span data-ttu-id="f9d71-122">Поиск .NET Framework 4.5 и более поздних версий:</span><span class="sxs-lookup"><span data-stu-id="f9d71-122">Find newer .NET Framework versions (4.5 and later):</span></span>
  - [<span data-ttu-id="f9d71-123">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="f9d71-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="f9d71-124">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="f9d71-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="f9d71-125">Запрос версий .NET Framework из реестра с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9d71-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="f9d71-126">Поиск более ранних версий .NET Framework (1–4):</span><span class="sxs-lookup"><span data-stu-id="f9d71-126">Find older .NET Framework versions (1&#8211;4):</span></span>
  - [<span data-ttu-id="f9d71-127">Поиск версий .NET Framework с помощью редактора реестра</span><span class="sxs-lookup"><span data-stu-id="f9d71-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="f9d71-128">Запрос версий .NET Framework из реестра с помощью кода</span><span class="sxs-lookup"><span data-stu-id="f9d71-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="f9d71-129">Получить список версий среды CLR, установленных на компьютере, можно с помощью специального средства или кода.</span><span class="sxs-lookup"><span data-stu-id="f9d71-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="f9d71-130">Использование средства Clrver</span><span class="sxs-lookup"><span data-stu-id="f9d71-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="f9d71-131">Использование кода для отправки запроса в класс Environment</span><span class="sxs-lookup"><span data-stu-id="f9d71-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="f9d71-132">Сведения об определении установленных обновлений для каждой версии платформы .NET Framework см. в статье [Практическое руководство. Определение установленных обновлений платформы .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="f9d71-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="f9d71-133">Поиск .NET Framework 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f9d71-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="f9d71-134">Поиск в реестре .NET Framework версии 4.5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f9d71-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="f9d71-135">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="f9d71-136">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f9d71-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="f9d71-137">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="f9d71-138">Если подраздел **Full** отсутствует, платформа .NET Framework 4.5 или более поздней версии не установлена.</span><span class="sxs-lookup"><span data-stu-id="f9d71-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9d71-139">Папка **NET Framework Setup** в реестре *не* начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="f9d71-139">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="f9d71-140">Проверьте значение DWORD с именем **Release**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="f9d71-141">Если оно имеется, платформа .NET Framework 4.5 или более поздней версии установлена.</span><span class="sxs-lookup"><span data-stu-id="f9d71-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="f9d71-142">Это значение является разделом выпуска, который соответствует определенной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="f9d71-143">Например, на приведенном ниже рисунке значение параметра **Release** равно *378389*, что является разделом выпуска для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f9d71-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span>

     <span data-ttu-id="f9d71-144">![Запись реестра для .NET Framework 4.5](media/clr-installdir.png "Запись реестра для .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="f9d71-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="f9d71-145">В следующей таблице перечислены значение DWORD **Release** в отдельных операционных системах для .NET Framework 4.5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f9d71-145">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="f9d71-146">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9d71-146">.NET Framework version</span></span>|<span data-ttu-id="f9d71-147">Значение DWORD "Release"</span><span class="sxs-lookup"><span data-stu-id="f9d71-147">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="f9d71-148">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="f9d71-148">.NET Framework 4.5</span></span>|<span data-ttu-id="f9d71-149">Все версии операционной системы Windows: 378389</span><span class="sxs-lookup"><span data-stu-id="f9d71-149">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="f9d71-150">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f9d71-150">.NET Framework 4.5.1</span></span>|<span data-ttu-id="f9d71-151">Windows 8.1 и Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="f9d71-151">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="f9d71-152">Все другие версии операционной системы Windows: 378758</span><span class="sxs-lookup"><span data-stu-id="f9d71-152">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="f9d71-153">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f9d71-153">.NET Framework 4.5.2</span></span>|<span data-ttu-id="f9d71-154">Все версии операционной системы Windows: 379893</span><span class="sxs-lookup"><span data-stu-id="f9d71-154">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="f9d71-155">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f9d71-155">.NET Framework 4.6</span></span>|<span data-ttu-id="f9d71-156">Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="f9d71-156">On Windows 10: 393295</span></span><br /><span data-ttu-id="f9d71-157">Все другие версии операционной системы Windows: 393297</span><span class="sxs-lookup"><span data-stu-id="f9d71-157">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="f9d71-158">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f9d71-158">.NET Framework 4.6.1</span></span>|<span data-ttu-id="f9d71-159">Windows 10 с ноябрьским обновлением: 394254</span><span class="sxs-lookup"><span data-stu-id="f9d71-159">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="f9d71-160">Все остальные версии операционной системы Windows (включая Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="f9d71-160">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="f9d71-161">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f9d71-161">.NET Framework 4.6.2</span></span>|<span data-ttu-id="f9d71-162">В юбилейном обновлении Windows 10 и Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="f9d71-162">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="f9d71-163">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 394806</span><span class="sxs-lookup"><span data-stu-id="f9d71-163">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="f9d71-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f9d71-164">.NET Framework 4.7</span></span>|<span data-ttu-id="f9d71-165">Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="f9d71-165">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="f9d71-166">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 460805</span><span class="sxs-lookup"><span data-stu-id="f9d71-166">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="f9d71-167">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f9d71-167">.NET Framework 4.7.1</span></span>|<span data-ttu-id="f9d71-168">Windows 10 Fall Creators Update и Windows Server версии 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="f9d71-168">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="f9d71-169">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 461310</span><span class="sxs-lookup"><span data-stu-id="f9d71-169">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="f9d71-170">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f9d71-170">.NET Framework 4.7.2</span></span>|<span data-ttu-id="f9d71-171">Windows 10 за апрель 2018 г. Update и Windows Server версии 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="f9d71-171">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="f9d71-172">Все остальные операционные системы, кроме Windows 10 с обновлением за апрель 2018 г. и Windows Server версии 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="f9d71-172">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="f9d71-173">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f9d71-173">.NET Framework 4.8</span></span>|<span data-ttu-id="f9d71-174">Обновление Windows 10 за май 2019 г.: 528040</span><span class="sxs-lookup"><span data-stu-id="f9d71-174">On Windows 10 May 2019 Update: 528040</span></span><br/><span data-ttu-id="f9d71-175">Все остальные версии операционной системы Windows (включая другие операционные системы Windows 10): 528049</span><span class="sxs-lookup"><span data-stu-id="f9d71-175">On all others Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

<span data-ttu-id="f9d71-176">Эти значения можно использовать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9d71-176">You can use these values as follows:</span></span>

- <span data-ttu-id="f9d71-177">Чтобы определить наличие конкретной версии .NET Framework в определенной версии операционной системы Windows, проверьте, *равно* ли значение DWORD **Release** значению, указанному в таблице.</span><span class="sxs-lookup"><span data-stu-id="f9d71-177">To determine whether a specific version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="f9d71-178">Например, чтобы определить наличие .NET Framework 4.6 в системе Windows 10, проверьте, является ли значение **Release** *равным* 393295.</span><span class="sxs-lookup"><span data-stu-id="f9d71-178">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

- <span data-ttu-id="f9d71-179">Чтобы определить наличие минимально необходимой версии .NET Framework, используйте меньшее значение DWORD **RELEASE** для этой версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-179">To determine whether a minimum version of the .NET Framework is present, use the smaller **RELEASE** DWORD value for that version.</span></span> <span data-ttu-id="f9d71-180">Например, если приложение работает в .NET Framework 4.6 или более поздней версии, проверьте, является ли значение DWORD **RELEASE** *большим или равным* 393295.</span><span class="sxs-lookup"><span data-stu-id="f9d71-180">For example, if your application runs under .NET Framework 4.6 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 393295.</span></span> <span data-ttu-id="f9d71-181">Таблицу, в которой указаны только минимально необходимые значения DWORD **RELEASE** для каждой версии .NET Framework, см. в статье [Минимальные значения Release DWORD для .NET Framework 4.5 и более поздних версий](minimum-release-dword.md).</span><span class="sxs-lookup"><span data-stu-id="f9d71-181">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

- <span data-ttu-id="f9d71-182">Для проверки нескольких версий сначала проверьте значение, которое *больше или равно* наименьшему значению DWORD для новейшей версии .NET Framework, а затем сравните значение с наименьшим значением DWORD для каждой последующей более новой версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-182">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="f9d71-183">Например, если приложению требуется .NET Framework 4.7 или более поздней версии и необходимо определит наличие конкретной версии .NET Framework, сначала проверьте, что значение DWORD **RELEASE** *больше или равно* 461808 (наименьшему значению DWORD для .NET Framework 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="f9d71-183">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="f9d71-184">Сравните значение DWORD **RELEASE** с наименьшим значением для каждой более поздней версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-184">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span> <span data-ttu-id="f9d71-185">Таблицу, в которой указаны только минимально необходимые значения DWORD **RELEASE** для каждой версии .NET Framework, см. в статье [Минимальные значения Release DWORD для .NET Framework 4.5 и более поздних версий](minimum-release-dword.md).</span><span class="sxs-lookup"><span data-stu-id="f9d71-185">For a table that lists only the minimum **RELEASE** DWORD value for each .NET Framework version, see [The minimum values of the Release DWORD for .NET Framework 4.5 and later versions](minimum-release-dword.md).</span></span>

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="f9d71-186">Поиск в реестре .NET Framework 4.5 и более поздних версий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="f9d71-186">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="f9d71-187">Используйте методы <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> и <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="f9d71-187">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="f9d71-188">Наличие параметра **Release** типа DWORD в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** свидетельствует о том, что на компьютере установлена платформа .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-188">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="f9d71-189">Проверьте значение параметра **Release**, чтобы определить установленную версию.</span><span class="sxs-lookup"><span data-stu-id="f9d71-189">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="f9d71-190">Для обеспечения совместимости с последующими версиями значение должно быть больше или равно значению, указанному в [таблице версий .NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="f9d71-190">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="f9d71-191">В следующем примере проверяется значение **Release** в реестре для поиска установленной версии .NET Framework 4.5 или более поздних.</span><span class="sxs-lookup"><span data-stu-id="f9d71-191">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="f9d71-192">В этом примере применяются рекомендации для проверки версии:</span><span class="sxs-lookup"><span data-stu-id="f9d71-192">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="f9d71-193">Проверяется, имеет ли параметр **Release** значение, *большее или равное* значению известных разделов выпуска.</span><span class="sxs-lookup"><span data-stu-id="f9d71-193">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="f9d71-194">Проверка выполняется с самой последней до самой ранней версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-194">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="f9d71-195">Проверка наличия минимально необходимой версии .NET Framework (4.5 или более поздней) с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9d71-195">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="f9d71-196">Используйте команды PowerShell для проверки значения параметра **Release** в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-196">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="f9d71-197">В приведенных ниже примерах значение **Release** проверяется с целью определить, установлена ли версия 4.6.2 или более поздняя версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9d71-197">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="f9d71-198">Код возвращает значение `True`, если одна из таких версий установлена, и `False` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="f9d71-198">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 }
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="f9d71-199">Чтобы проверить наличие другой минимальной необходимой версии .NET Framework, замените значение *394802* в этих примерах на значение **Release** из [таблицы версий NET Framework](#version_table).</span><span class="sxs-lookup"><span data-stu-id="f9d71-199">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="f9d71-200">Поиск более ранних версий .NET Framework (1–4)</span><span class="sxs-lookup"><span data-stu-id="f9d71-200">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="f9d71-201">Поиск в реестре .NET Framework версий 1–4</span><span class="sxs-lookup"><span data-stu-id="f9d71-201">Find .NET Framework versions 1&#8211;4 in the registry</span></span>

1. <span data-ttu-id="f9d71-202">В меню **Пуск** выберите **Выполнить**, введите *regedit* и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-202">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="f9d71-203">Для запуска программы regedit необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f9d71-203">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="f9d71-204">В редакторе реестра откройте следующий подраздел: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-204">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="f9d71-205">Каждая установленная версия .NET Framework с 1.1 по 3.5 указывается как отдельный подраздел в разделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-205">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="f9d71-206">Пример: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-206">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="f9d71-207">Номер версии хранится в параметре **Version** подраздела версии.</span><span class="sxs-lookup"><span data-stu-id="f9d71-207">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="f9d71-208">Для версии .NET Framework 4 параметр **Version** находится в подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, подразделе **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** или в обоих этих подразделах.</span><span class="sxs-lookup"><span data-stu-id="f9d71-208">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9d71-209">Папка **NET Framework Setup** в реестре не начинается с точки.</span><span class="sxs-lookup"><span data-stu-id="f9d71-209">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="f9d71-210">На приведенном ниже рисунке показан подраздел для версии .NET Framework 3.5 вместе с параметром **Version**.</span><span class="sxs-lookup"><span data-stu-id="f9d71-210">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="f9d71-211">![Запись реестра для .NET Framework 3.5](media/net-4-and-earlier.png ".NET Framework 3.5 и более ранних версий")</span><span class="sxs-lookup"><span data-stu-id="f9d71-211">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="f9d71-212">Поиск .NET Framework версий 1–4 с помощью кода</span><span class="sxs-lookup"><span data-stu-id="f9d71-212">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="f9d71-213">Используйте класс <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> для доступа к подразделу **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="f9d71-213">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="f9d71-214">В следующем примере ищутся установленные версии .NET Framework 1–4:</span><span class="sxs-lookup"><span data-stu-id="f9d71-214">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="f9d71-215">Поиск версий CLR</span><span class="sxs-lookup"><span data-stu-id="f9d71-215">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="f9d71-216">Поиск текущей версии среды CLR с помощью Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="f9d71-216">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="f9d71-217">Для определения версий среды CLR, установленных на компьютере, можно использовать [средство CLR Version (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f9d71-217">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="f9d71-218">Запустите [Командную строку разработчика для Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) и введите `clrver`.</span><span class="sxs-lookup"><span data-stu-id="f9d71-218">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="f9d71-219">Пример полученных результатов:</span><span class="sxs-lookup"><span data-stu-id="f9d71-219">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="f9d71-220">Поиск текущей версии среды CLR с помощью класса Environment</span><span class="sxs-lookup"><span data-stu-id="f9d71-220">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9d71-221">Для .NET Framework 4.5 и более поздних версий не следует использовать свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> для определения версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f9d71-221">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="f9d71-222">Вместо этого выполните запрос к реестру, как описано в разделе [Поиск .NET Framework версии 4.5 и более поздних с помощью кода](#net_d).</span><span class="sxs-lookup"><span data-stu-id="f9d71-222">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="f9d71-223">Выполните запрос к свойству <xref:System.Environment.Version?displayProperty=nameWithType>, чтобы получить объект <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="f9d71-223">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="f9d71-224">Возвращенный объект `System.Version` указывает версию среды выполнения, в которой в настоящее время выполняется код.</span><span class="sxs-lookup"><span data-stu-id="f9d71-224">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="f9d71-225">Он не содержит версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d71-225">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="f9d71-226">Для платформы .NET Framework версий 4, 4.5, 4.5.1 и 4.5.2 возвращаемый объект <xref:System.Version> имеет строковое представление 4.0.30319.*xxxxx*, где *xxxxx* меньше 42000.</span><span class="sxs-lookup"><span data-stu-id="f9d71-226">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="f9d71-227">Для .NET Framework 4.6 и более поздних версий оно имеет форму 4.0.30319.42000.</span><span class="sxs-lookup"><span data-stu-id="f9d71-227">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="f9d71-228">Получив объект `Version`, выполните к нему запрос.</span><span class="sxs-lookup"><span data-stu-id="f9d71-228">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="f9d71-229">Чтобы получить идентификатор основного выпуска (например, *4* в случае версии 4.0), используйте свойство <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d71-229">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="f9d71-230">Чтобы получить идентификатор дополнительной версии (например, *0* в случае версии 4.0), используйте свойство <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d71-230">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="f9d71-231">Чтобы получить всю строку версии (например, *4.0.30319.18010*), используйте метод <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d71-231">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f9d71-232">Он возвращает одно значение, соответствующее версии среды выполнения, в которой выполняется код.</span><span class="sxs-lookup"><span data-stu-id="f9d71-232">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="f9d71-233">Он не возвращает версий сборок или других версий среды выполнения, которые установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d71-233">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="f9d71-234">В следующем примере свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> используется для получения сведений о версии среды CLR:</span><span class="sxs-lookup"><span data-stu-id="f9d71-234">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="f9d71-235">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d71-235">See also</span></span>

- [<span data-ttu-id="f9d71-236">Практическое руководство. Определение установленных обновлений платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9d71-236">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="f9d71-237">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="f9d71-237">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="f9d71-238">Версии и зависимости платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9d71-238">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
