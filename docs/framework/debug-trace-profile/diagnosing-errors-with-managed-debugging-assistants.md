---
title: Диагностика ошибок посредством управляемых помощников по отладке
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532979"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="9042e-102">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="9042e-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="9042e-103">Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="9042e-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="9042e-104">Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами.</span><span class="sxs-lookup"><span data-stu-id="9042e-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="9042e-105">Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="9042e-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="9042e-106">Вы можете [включить или отключить](#enable-and-disable-mdas) все помощники, добавив раздел в реестре Windows, или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="9042e-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="9042e-107">Вы можете включить отдельные помощники, используя параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="9042e-108">Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="9042e-109">Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="9042e-110">Вы не сможете включить его для уже запущенных приложений.</span><span class="sxs-lookup"><span data-stu-id="9042e-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="9042e-111">В следующей таблице перечислены Помощники отладки управляемого кода, поставляемых вместе с .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9042e-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="9042e-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="9042e-112">asynchronousThreadAbort</span></span>](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[<span data-ttu-id="9042e-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="9042e-113">bindingFailure</span></span>](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[<span data-ttu-id="9042e-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="9042e-114">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="9042e-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="9042e-115">contextSwitchDeadlock</span></span>](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="9042e-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="9042e-116">dangerousThreadingAPI</span></span>](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[<span data-ttu-id="9042e-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="9042e-117">dateTimeInvalidLocalFormat</span></span>](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="9042e-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="9042e-118">dirtyCastAndCallOnInterface</span></span>](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="9042e-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="9042e-119">disconnectedContext</span></span>](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[<span data-ttu-id="9042e-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="9042e-120">dllMainReturnsFalse</span></span>](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[<span data-ttu-id="9042e-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="9042e-121">exceptionSwallowedOnCallFromCom</span></span>](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="9042e-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="9042e-122">failedQI</span></span>](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[<span data-ttu-id="9042e-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="9042e-123">fatalExecutionEngineError</span></span>](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="9042e-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="9042e-124">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="9042e-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="9042e-125">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="9042e-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="9042e-126">illegalPrepareConstrainedRegion</span></span>](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="9042e-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="9042e-127">invalidApartmentStateChange</span></span>](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="9042e-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="9042e-128">invalidCERCall</span></span>](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[<span data-ttu-id="9042e-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="9042e-129">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="9042e-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="9042e-130">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[<span data-ttu-id="9042e-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="9042e-131">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[<span data-ttu-id="9042e-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="9042e-132">invalidMemberDeclaration</span></span>](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[<span data-ttu-id="9042e-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="9042e-133">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="9042e-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="9042e-134">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[<span data-ttu-id="9042e-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="9042e-135">jitCompilationStart</span></span>](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[<span data-ttu-id="9042e-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="9042e-136">loaderLock</span></span>](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[<span data-ttu-id="9042e-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="9042e-137">loadFromContext</span></span>](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[<span data-ttu-id="9042e-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="9042e-138">marshalCleanupError</span></span>](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[<span data-ttu-id="9042e-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="9042e-139">marshaling</span></span>](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[<span data-ttu-id="9042e-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="9042e-140">memberInfoCacheCreation</span></span>](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[<span data-ttu-id="9042e-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="9042e-141">moduloObjectHashcode</span></span>](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="9042e-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="9042e-142">nonComVisibleBaseClass</span></span>](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="9042e-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="9042e-143">notMarshalable</span></span>](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[<span data-ttu-id="9042e-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="9042e-144">openGenericCERCall</span></span>](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[<span data-ttu-id="9042e-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="9042e-145">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[<span data-ttu-id="9042e-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="9042e-146">pInvokeLog</span></span>](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[<span data-ttu-id="9042e-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="9042e-147">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="9042e-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="9042e-148">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[<span data-ttu-id="9042e-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="9042e-149">reentrancy</span></span>](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[<span data-ttu-id="9042e-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="9042e-150">releaseHandleFailed</span></span>](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[<span data-ttu-id="9042e-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="9042e-151">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[<span data-ttu-id="9042e-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="9042e-152">streamWriterBufferedDataLost</span></span>](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="9042e-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="9042e-153">virtualCERCall</span></span>](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

<span data-ttu-id="9042e-154">По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков.</span><span class="sxs-lookup"><span data-stu-id="9042e-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="9042e-155">Можно просмотреть набор по умолчанию в Visual Studio, выбрав **Windows** > **параметры исключений** на **Отладка** меню, а затем развернуть **Помощники отладки управляемого кода** списка.</span><span class="sxs-lookup"><span data-stu-id="9042e-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Окно параметров исключений в Visual Studio](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="9042e-157">Включение и отключение помощников отладки управляемого кода</span><span class="sxs-lookup"><span data-stu-id="9042e-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="9042e-158">Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="9042e-159">Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.</span><span class="sxs-lookup"><span data-stu-id="9042e-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="9042e-160">Вместо отключения Помощники отладки управляемого кода, можно запретить отображение диалогового окна MDA при получении уведомления от Помощника Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9042e-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="9042e-161">Чтобы сделать это, выберите **Windows** > **параметры исключений** на **Отладка** меню разверните **Помощники отладки управляемого кода**список, а затем установите или снимите **прервать при исключение** флажок для отдельного Помощника.</span><span class="sxs-lookup"><span data-stu-id="9042e-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="9042e-162">Раздел реестра .</span><span class="sxs-lookup"><span data-stu-id="9042e-162">Registry Key</span></span>

<span data-ttu-id="9042e-163">Чтобы включить Помощники отладки управляемого кода, добавьте **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\MDA** раздел реестра Windows (тип REG_SZ, значение 1).</span><span class="sxs-lookup"><span data-stu-id="9042e-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="9042e-164">Скопируйте следующий пример в текстовый файл с именем *MDAEnable.reg*. Откройте редактор реестра Windows (RegEdit.exe) и из **файл** меню выберите команду **импорта**.</span><span class="sxs-lookup"><span data-stu-id="9042e-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="9042e-165">Выберите *MDAEnable.reg* файл, чтобы включить Помощники отладки управляемого кода на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9042e-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="9042e-166">Установка для подраздела строкового значения **1** (не значения DWORD, равного **1**) позволяет считывать параметры Помощника из *имяПриложения.суффикс*. mda.config файл.</span><span class="sxs-lookup"><span data-stu-id="9042e-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="9042e-167">Например файл конфигурации Помощника для блокнота бы имя notepad.exe.mda.config.</span><span class="sxs-lookup"><span data-stu-id="9042e-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="9042e-168">Если на компьютере в 64-разрядной операционной системе выполнянется 32-разрядное приложение, раздел помощника нужно задать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9042e-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="9042e-169">См. в разделе [параметров конфигурации конкретных приложений](#application-specific-configuration-settings) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9042e-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="9042e-170">Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="9042e-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="9042e-171">См. в разделе [переменной среды](#environment-variable) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="9042e-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="9042e-172">Чтобы отключить Помощники отладки управляемого кода, задайте для подраздела Помощников **0** (ноль), с помощью редактора реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="9042e-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="9042e-173">По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="9042e-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="9042e-174">Эти помощники можно отключить, выполнив *MDADisable.reg* файл, как описано выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9042e-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="9042e-175">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="9042e-175">Environment Variable</span></span>

<span data-ttu-id="9042e-176">Активацией помощников также можно управлять с помощью переменной среды COMPLUS_MDA, которая переопределяет раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="9042e-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="9042e-177">Строка COMPLUS_MDA представляет собой разделенный точками с запятыми перечень имен помощников отладки управляемого кода или других специальных управляющих строк, составленный без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="9042e-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="9042e-178">При запуске под контролем управляемого или неуправляемого отладчика по умолчанию включается набор помощников.</span><span class="sxs-lookup"><span data-stu-id="9042e-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="9042e-179">Для этого необходимо неявным образом добавить разделенный точками с запятыми список помощников, которые включаются по умолчанию под контролем отладчиков, в начало значения переменной среды или раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="9042e-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="9042e-180">Специальные управляющие строки:</span><span class="sxs-lookup"><span data-stu-id="9042e-180">The special control strings are the following:</span></span>

- <span data-ttu-id="9042e-181">`0` — отключает все помощники.</span><span class="sxs-lookup"><span data-stu-id="9042e-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="9042e-182">`1` — считывает параметры помощника из файла *ИмяПриложения*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="9042e-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="9042e-183">`managedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске управляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="9042e-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="9042e-184">`unmanagedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске неуправляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="9042e-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="9042e-185">При наличии конфликтующих параметров более старые параметры переопределяются более новыми:</span><span class="sxs-lookup"><span data-stu-id="9042e-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="9042e-186">`COMPLUS_MDA=0` отключает все помощники, включая те, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="9042e-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="9042e-187">`COMPLUS_MDA=gcUnmanagedToManaged` включает `gcUnmanagedToManaged` в дополнение к помощникам, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="9042e-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="9042e-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` включает `gcUnmanagedToManaged`, но отключает те помощники, которые были бы неявно включены под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="9042e-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="9042e-189">Параметры конфигурации для конкретного приложения</span><span class="sxs-lookup"><span data-stu-id="9042e-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="9042e-190">Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="9042e-191">Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="9042e-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="9042e-192">Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения.</span><span class="sxs-lookup"><span data-stu-id="9042e-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="9042e-193">Имя файла имеет следующий вид *ИмяПриложения*.mda.config, например notepad.exe.mda.config. Помощники, включенные в файле конфигурации приложения, могут иметь атрибуты или элементы, предназначенные специально для управления данным аспектом работы помощника.</span><span class="sxs-lookup"><span data-stu-id="9042e-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="9042e-194">В следующем примере показано, как включить и настроить [маршалинг](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="9042e-194">The following example shows how to enable and configure the [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md):</span></span>

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

<span data-ttu-id="9042e-195">Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении.</span><span class="sxs-lookup"><span data-stu-id="9042e-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="9042e-196">`Marshaling` MDA можно также фильтровать имена метода и структурным полям **methodFilter** и **fieldFilter** дочерние элементы, соответственно.</span><span class="sxs-lookup"><span data-stu-id="9042e-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="9042e-197">В следующем примере показано, как включить несколько помощников отладки управляемого кода с помощью их параметров по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="9042e-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> <span data-ttu-id="9042e-198">При указании нескольких помощников в файле конфигурации их следует перечислять в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="9042e-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="9042e-199">Например, если вы хотите включить помощники `virtualCERCall` и `invalidCERCall`, необходимо добавить запись `<invalidCERCall />` перед записью `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="9042e-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="9042e-200">Если записи расположены не в алфавитном порядке, отображается сообщение о необработанном исключении недопустимого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9042e-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="9042e-201">Исключения по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="9042e-201">MDA exceptions</span></span>

<span data-ttu-id="9042e-202">Если MDA включен, он остается активным даже когда ваш код не выполняется в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="9042e-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="9042e-203">Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="9042e-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="9042e-204">Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="9042e-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="9042e-205">Если код выполняется в среде разработки Visual Studio (IDE), можно предотвратить диалоговое окно исключения, который отображается для определенных событий по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9042e-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="9042e-206">Для этого на **Отладка** меню, выберите **Windows** > **параметры исключений**.</span><span class="sxs-lookup"><span data-stu-id="9042e-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="9042e-207">В **параметры исключений** окне разверните **Помощники отладки управляемого кода** списке, а затем снимите **прервать при исключение** флажок для отдельного Помощника.</span><span class="sxs-lookup"><span data-stu-id="9042e-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="9042e-208">Можно также использовать это диалоговое окно, чтобы *включить* отображение диалоговых окон исключений по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9042e-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="9042e-209">Выходные данные помощников</span><span class="sxs-lookup"><span data-stu-id="9042e-209">MDA Output</span></span>

<span data-ttu-id="9042e-210">MDA результат аналогичен приведенному в следующем примере показаны выходные данные `PInvokeStackImbalance` по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="9042e-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="9042e-211">**Вызов функции PInvoke "MDATest! MDATest.Program::StdCall "внесла дисбаланс в стек. Это обусловлено тем, скорее всего, управляемая сигнатура PInvoke не соответствует сигнатуре неуправляемого целевой. Проверьте, что соглашение о вызовах и параметры подписи PInvoke соответствовать неуправляемой сигнатуре целевой объект.**</span><span class="sxs-lookup"><span data-stu-id="9042e-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="9042e-212">См. также</span><span class="sxs-lookup"><span data-stu-id="9042e-212">See also</span></span>

- [<span data-ttu-id="9042e-213">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="9042e-213">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
