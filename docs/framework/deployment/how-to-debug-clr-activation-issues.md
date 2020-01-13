---
title: Практическое руководство. Отладка проблем при активации CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 602ee3c88237a902d48339836fbe25f636ae9705
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716508"
---
# <a name="how-to-debug-clr-activation-issues"></a><span data-ttu-id="f4056-102">Практическое руководство. Отладка проблем при активации CLR</span><span class="sxs-lookup"><span data-stu-id="f4056-102">How to debug CLR activation issues</span></span>

<span data-ttu-id="f4056-103">При возникновении проблем при попытке запустить приложение с правильной версией среды CLR можно просматривать и отлаживать журналы активации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-103">If you encounter problems in getting your application to run with the correct version of the common language runtime (CLR), you can view and debug CLR activation logs.</span></span> <span data-ttu-id="f4056-104">Эти журналы могут быть очень полезными при выявлении основной причины проблемы активации, когда приложение или загружает не ту версию среды CLR, которую ожидалось, или вообще не загружает среду CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-104">These logs can be very useful in determining the root cause of an activation issue, when your application either loads a different CLR version than expected or doesn't load the CLR at all.</span></span> <span data-ttu-id="f4056-105">В разделе [Ошибки инициализации платформы .NET Framework: управление пользовательской средой](initialization-errors-managing-the-user-experience.md) рассматривается случай, когда среда CLR не была найдена.</span><span class="sxs-lookup"><span data-stu-id="f4056-105">The [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) discusses the experience when no CLR is found for an application.</span></span>

<span data-ttu-id="f4056-106">Ведение журналов активации среды CLR может быть включено для всей системы с помощью раздела реестра HKEY_LOCAL_MACHINE или переменной среды операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f4056-106">CLR activation logging can be enabled system-wide by using an HKEY_LOCAL_MACHINE registry key or a system environment variable.</span></span> <span data-ttu-id="f4056-107">Журнал будет вестись до тех пор, пока запись реестра или переменная среды не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="f4056-107">The log will be generated until the registry entry or the environment variable is removed.</span></span> <span data-ttu-id="f4056-108">Кроме того, можно использовать переменную среды процесса, чтобы включить ведение журнала с иными областью и временем существования.</span><span class="sxs-lookup"><span data-stu-id="f4056-108">Alternatively, you can use a user or process-local environment variable to enable logging with a different scope and duration.</span></span>

<span data-ttu-id="f4056-109">Журналы активации среды CLR не следует путать с [журналами привязки сборок](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), которые полностью отличаются.</span><span class="sxs-lookup"><span data-stu-id="f4056-109">CLR activation logs shouldn't be confused with [assembly binding logs](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), which are entirely different.</span></span>

## <a name="to-enable-clr-activation-logging"></a><span data-ttu-id="f4056-110">Включение ведения журналов активации среды CLR</span><span class="sxs-lookup"><span data-stu-id="f4056-110">To enable CLR activation logging</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="f4056-111">Использование реестра</span><span class="sxs-lookup"><span data-stu-id="f4056-111">Using the registry</span></span>

1. <span data-ttu-id="f4056-112">В редакторе реестра перейдите к разделу HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (на 32-разрядном компьютере) или HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (на 64-разрядном компьютере).</span><span class="sxs-lookup"><span data-stu-id="f4056-112">In the Registry Editor, navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (on a 32-bit computer) or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework folder (on a 64-bit computer).</span></span>

2. <span data-ttu-id="f4056-113">Добавьте строковое значение с именем `CLRLoadLogDir` и задайте в нем полный путь к существующему каталогу, в котором будут храниться журналы активации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-113">Add a string value named `CLRLoadLogDir`, and set it to the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

<span data-ttu-id="f4056-114">Журналы активации будут вестись до тех пор, пока не вы удалите это строковое значение.</span><span class="sxs-lookup"><span data-stu-id="f4056-114">Activation logging remains enabled until you remove the string value.</span></span>

### <a name="using-an-environment-variable"></a><span data-ttu-id="f4056-115">Использование переменной среды</span><span class="sxs-lookup"><span data-stu-id="f4056-115">Using an environment variable</span></span>

- <span data-ttu-id="f4056-116">Задайте в переменной среды `COMPLUS_CLRLoadLogDir` строку, представляющую полный путь к существующему каталогу, в котором будут храниться журналы активации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-116">Set the `COMPLUS_CLRLoadLogDir` environment variable to a string that represents the full path of an existing directory where you'd like to store CLR activation logs.</span></span>

    <span data-ttu-id="f4056-117">Способ задания переменной среды определяет ее область действия:</span><span class="sxs-lookup"><span data-stu-id="f4056-117">How you set the environment variable determines its scope:</span></span>

  - <span data-ttu-id="f4056-118">Если переменная задается на уровне системы, ведение журналов активации включается для всех приложений платформы .NET Framework на этом компьютере до тех пор, пока переменная среды не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="f4056-118">If you set it at the system level, activation logging is enabled for all .NET Framework applications on that computer until the environment variable is removed.</span></span>

  - <span data-ttu-id="f4056-119">Если она задана на уровне пользователя, ведение журналов активации включается только для учетной записи текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4056-119">If you set it at the user level, activation logging is enabled only for the current user account.</span></span> <span data-ttu-id="f4056-120">Ведение журналов продолжается до тех пор, пока переменная среды не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="f4056-120">Logging continues until the environment variable is removed.</span></span>

  - <span data-ttu-id="f4056-121">Если переменная задается из процесса перед загрузкой среды CLR, журналы активации будут вестись до завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="f4056-121">If you set it from within the process before loading the CLR, activation logging is enabled until the process terminates.</span></span>

  - <span data-ttu-id="f4056-122">Если переменная задана из командной строки перед запуском приложения, журналы активации будут вестись для всех приложений, запущенных из этой командной строки.</span><span class="sxs-lookup"><span data-stu-id="f4056-122">If you set it at a command prompt before you run an application, activation logging is enabled for any application that is run from that command prompt.</span></span>

    <span data-ttu-id="f4056-123">Например, чтобы хранить журналы активации в каталоге c:\clrloadlogs с областью действия уровня процесса, следует открыть окно командной строки и ввести следующую строку перед запуском приложения:</span><span class="sxs-lookup"><span data-stu-id="f4056-123">For example, to store activation logs in the c:\clrloadlogs directory with process-level scope, open a Command Prompt window and type the following before you run the application:</span></span>

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a><span data-ttu-id="f4056-124">Пример</span><span class="sxs-lookup"><span data-stu-id="f4056-124">Example</span></span>

<span data-ttu-id="f4056-125">Журналы активации среды CLR предоставляют большой объем данных об активации среды CLR и использовании API размещения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-125">CLR activation logs provide a large amount of data about CLR activation and the use of the CLR hosting APIs.</span></span> <span data-ttu-id="f4056-126">Большая часть этих данных используется внутренне Майкрософт, но некоторые из данных также могут быть полезны для разработчиков, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f4056-126">Most of this data is used internally by Microsoft, but some of the data can also be useful to developers, as described in this article.</span></span>

<span data-ttu-id="f4056-127">Журнал автоматически устанавливает порядок, в котором были вызваны API размещения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-127">The log reflects the order in which the CLR hosting APIs were called.</span></span> <span data-ttu-id="f4056-128">Он также содержит полезные данные о наборе установленных сред выполнения, обнаруженных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f4056-128">It also includes useful data about the set of installed runtimes detected on the computer.</span></span> <span data-ttu-id="f4056-129">Формат самого журнала активации среды CLR не документирован, но может быть использован для помощи разработчикам, которым требуется разрешить проблемы активации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f4056-129">The CLR activation log format is not itself documented, but can be used to aid developers who need to resolve CLR activation issues.</span></span>

> [!NOTE]
> <span data-ttu-id="f4056-130">Нельзя открыть журнал активации до тех пор, пока процесс, использующий среду CLR, не был завершен.</span><span class="sxs-lookup"><span data-stu-id="f4056-130">You cannot open an activation log until the process that uses the CLR has terminated.</span></span>

> [!NOTE]
> <span data-ttu-id="f4056-131">Журналы активации среды CLR не локализуются; они всегда создаются на английском языке.</span><span class="sxs-lookup"><span data-stu-id="f4056-131">CLR activation logs are not localized; they are always generated in the English language.</span></span>

<span data-ttu-id="f4056-132">В следующем примере журналов активации наиболее полезные сведения выделены и описаны после журнала.</span><span class="sxs-lookup"><span data-stu-id="f4056-132">In the following example of an activation log, the most useful information is highlighted and described after the log.</span></span>

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- <span data-ttu-id="f4056-133">**CLR Loading log** указывает путь до исполняемого файла, запустившего процесс, который загружает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="f4056-133">**CLR Loading log** provides the path to the executable that started the process that loaded managed code.</span></span> <span data-ttu-id="f4056-134">Обратите внимание, что это может быть собственное основное приложение.</span><span class="sxs-lookup"><span data-stu-id="f4056-134">Note that this could be a native host.</span></span>

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- <span data-ttu-id="f4056-135">**Installed Runtime** — набор версий среды CLR, установленных на компьютере, являющихся кандидатами для запроса активации.</span><span class="sxs-lookup"><span data-stu-id="f4056-135">**Installed Runtime** is the set of CLR versions installed on the computer that are candidates for the activation request.</span></span>

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- <span data-ttu-id="f4056-136">**built with version** — версия среды CLR, которая использовалась для построения бинарного файла, который был предоставлен методу, подобному [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4056-136">**built with version** is the version of the CLR that was used to build the binary that was provided to a method such as [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).</span></span>

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- <span data-ttu-id="f4056-137">**feature-on-demand installation** указывает на включение .NET Framework 3.5 в Windows 8.</span><span class="sxs-lookup"><span data-stu-id="f4056-137">**feature-on-demand installation** refers to enabling the .NET Framework 3.5 on Windows 8.</span></span> <span data-ttu-id="f4056-138">См. в разделе [Ошибки инициализации платформы .NET Framework: управление пользовательской средой](initialization-errors-managing-the-user-experience.md) дополнительные сведения об этом случае.</span><span class="sxs-lookup"><span data-stu-id="f4056-138">See [.NET Framework Initialization Errors: Managing the User Experience](initialization-errors-managing-the-user-experience.md) for more information about this scenario.</span></span>

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a><span data-ttu-id="f4056-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f4056-139">See also</span></span>

- [<span data-ttu-id="f4056-140">Развертывание</span><span class="sxs-lookup"><span data-stu-id="f4056-140">Deployment</span></span>](index.md)
- [<span data-ttu-id="f4056-141">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="f4056-141">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
