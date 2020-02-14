---
title: Диагностика ошибок посредством помощников по отладке управляемого кода
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
ms.openlocfilehash: 712fbbe9e0ad291385e8eef321c5e8a2fa092a5d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216556"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a><span data-ttu-id="72743-102">Диагностика ошибок с помощью помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="72743-102">Diagnose Errors with Managed Debugging Assistants</span></span>

<span data-ttu-id="72743-103">Помощники отладки управляемого кода (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для предоставления информации о состоянии времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="72743-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="72743-104">Эти помощники формируют информационные сообщения о событиях времени выполнения, которые вы не можете зафиксировать иными средствами.</span><span class="sxs-lookup"><span data-stu-id="72743-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="72743-105">Вы можете использовать помощники отладки управляемого кода для изоляции тяжело обнаружимых ошибок приложения, возникающих при переходе между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="72743-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span>

<span data-ttu-id="72743-106">Вы можете [включить или отключить](#enable-and-disable-mdas) все MDA, добавив ключ в реестр Windows или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="72743-106">You can [enable or disable](#enable-and-disable-mdas) all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="72743-107">Вы можете включить отдельные помощники, используя параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="72743-108">Вы можете задать дополнительные параметры для некоторых отдельных помощников в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="72743-109">Поскольку эти файлы конфигурации анализируются при загрузке среды выполнения, следует включить помощник до запуска управляемого приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="72743-110">Вы не сможете включить его для уже запущенных приложений.</span><span class="sxs-lookup"><span data-stu-id="72743-110">You cannot enable it for applications that have already started.</span></span>

<span data-ttu-id="72743-111">В следующей таблице перечислены MDA, поставляемые с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72743-111">The following table lists the MDAs that ship with the .NET Framework:</span></span>

|||
|-|-|
|[<span data-ttu-id="72743-112">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="72743-112">asynchronousThreadAbort</span></span>](asynchronousthreadabort-mda.md)|[<span data-ttu-id="72743-113">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="72743-113">bindingFailure</span></span>](bindingfailure-mda.md)|
|[<span data-ttu-id="72743-114">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="72743-114">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="72743-115">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="72743-115">contextSwitchDeadlock</span></span>](contextswitchdeadlock-mda.md)|
|[<span data-ttu-id="72743-116">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="72743-116">dangerousThreadingAPI</span></span>](dangerousthreadingapi-mda.md)|[<span data-ttu-id="72743-117">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="72743-117">dateTimeInvalidLocalFormat</span></span>](datetimeinvalidlocalformat-mda.md)|
|[<span data-ttu-id="72743-118">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="72743-118">dirtyCastAndCallOnInterface</span></span>](dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="72743-119">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="72743-119">disconnectedContext</span></span>](disconnectedcontext-mda.md)|
|[<span data-ttu-id="72743-120">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="72743-120">dllMainReturnsFalse</span></span>](dllmainreturnsfalse-mda.md)|[<span data-ttu-id="72743-121">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="72743-121">exceptionSwallowedOnCallFromCom</span></span>](exceptionswallowedoncallfromcom-mda.md)|
|[<span data-ttu-id="72743-122">failedQI</span><span class="sxs-lookup"><span data-stu-id="72743-122">failedQI</span></span>](failedqi-mda.md)|[<span data-ttu-id="72743-123">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="72743-123">fatalExecutionEngineError</span></span>](fatalexecutionengineerror-mda.md)|
|[<span data-ttu-id="72743-124">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="72743-124">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="72743-125">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="72743-125">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)|
|[<span data-ttu-id="72743-126">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="72743-126">illegalPrepareConstrainedRegion</span></span>](illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="72743-127">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="72743-127">invalidApartmentStateChange</span></span>](invalidapartmentstatechange-mda.md)|
|[<span data-ttu-id="72743-128">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="72743-128">invalidCERCall</span></span>](invalidcercall-mda.md)|[<span data-ttu-id="72743-129">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="72743-129">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)|
|[<span data-ttu-id="72743-130">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="72743-130">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)|[<span data-ttu-id="72743-131">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="72743-131">invalidIUnknown</span></span>](invalidiunknown-mda.md)|
|[<span data-ttu-id="72743-132">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="72743-132">invalidMemberDeclaration</span></span>](invalidmemberdeclaration-mda.md)|[<span data-ttu-id="72743-133">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="72743-133">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)|
|[<span data-ttu-id="72743-134">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="72743-134">invalidVariant</span></span>](invalidvariant-mda.md)|[<span data-ttu-id="72743-135">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="72743-135">jitCompilationStart</span></span>](jitcompilationstart-mda.md)|
|[<span data-ttu-id="72743-136">loaderLock</span><span class="sxs-lookup"><span data-stu-id="72743-136">loaderLock</span></span>](loaderlock-mda.md)|[<span data-ttu-id="72743-137">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="72743-137">loadFromContext</span></span>](loadfromcontext-mda.md)|
|[<span data-ttu-id="72743-138">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="72743-138">marshalCleanupError</span></span>](marshalcleanuperror-mda.md)|[<span data-ttu-id="72743-139">marshaling</span><span class="sxs-lookup"><span data-stu-id="72743-139">marshaling</span></span>](marshaling-mda.md)|
|[<span data-ttu-id="72743-140">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="72743-140">memberInfoCacheCreation</span></span>](memberinfocachecreation-mda.md)|[<span data-ttu-id="72743-141">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="72743-141">moduloObjectHashcode</span></span>](moduloobjecthashcode-mda.md)|
|[<span data-ttu-id="72743-142">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="72743-142">nonComVisibleBaseClass</span></span>](noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="72743-143">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="72743-143">notMarshalable</span></span>](notmarshalable-mda.md)|
|[<span data-ttu-id="72743-144">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="72743-144">openGenericCERCall</span></span>](opengenericcercall-mda.md)|[<span data-ttu-id="72743-145">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="72743-145">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)|
|[<span data-ttu-id="72743-146">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="72743-146">pInvokeLog</span></span>](pinvokelog-mda.md)|[<span data-ttu-id="72743-147">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="72743-147">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)|
|[<span data-ttu-id="72743-148">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="72743-148">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)|[<span data-ttu-id="72743-149">reentrancy</span><span class="sxs-lookup"><span data-stu-id="72743-149">reentrancy</span></span>](reentrancy-mda.md)|
|[<span data-ttu-id="72743-150">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="72743-150">releaseHandleFailed</span></span>](releasehandlefailed-mda.md)|[<span data-ttu-id="72743-151">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="72743-151">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)|
|[<span data-ttu-id="72743-152">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="72743-152">streamWriterBufferedDataLost</span></span>](streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="72743-153">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="72743-153">virtualCERCall</span></span>](virtualcercall-mda.md)|

<span data-ttu-id="72743-154">По умолчанию .NET Framework активирует подмножество помощников отладки управляемого кода для всех управляемых отладчиков.</span><span class="sxs-lookup"><span data-stu-id="72743-154">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="72743-155">Вы можете просмотреть набор по умолчанию в Visual Studio, выбрав пункт **параметры исключений** **Windows** > в меню **Отладка** , а затем развернув список **помощники по отладке управляемого** кода.</span><span class="sxs-lookup"><span data-stu-id="72743-155">You can view the default set in Visual Studio by choosing **Windows** > **Exception Settings** on the **Debug** menu, and then expanding the **Managed Debugging Assistants** list.</span></span>

![Окно параметров исключений в Visual Studio](./media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a><span data-ttu-id="72743-157">Включение и отключение MDA</span><span class="sxs-lookup"><span data-stu-id="72743-157">Enable and Disable MDAs</span></span>

<span data-ttu-id="72743-158">Вы можете включать и отключать помощники отладки управляемого кода с помощью раздела реестра, переменной среды и параметров конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-158">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="72743-159">Чтобы воспользоваться параметрами конфигурации приложения, вы должны включить раздел реестра или переменную среды.</span><span class="sxs-lookup"><span data-stu-id="72743-159">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>

> [!TIP]
> <span data-ttu-id="72743-160">Вместо отключения MDA можно запретить Visual Studio отображать диалоговое окно MDA при получении уведомления MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-160">Instead of disabling MDAs, you can prevent Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="72743-161">Для этого выберите пункт **параметры исключений** **Windows** > в меню **Отладка** , разверните список **помощники по отладке управляемого** кода, а затем установите или снимите флажок **прерывать при возникновении** для отдельного MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-161">To do that, choose **Windows** > **Exception Settings** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Break When Thrown** check box for the individual MDA.</span></span>

### <a name="registry-key"></a><span data-ttu-id="72743-162">Ключ реестра</span><span class="sxs-lookup"><span data-stu-id="72743-162">Registry Key</span></span>

<span data-ttu-id="72743-163">Чтобы включить MDA, добавьте **HKEY_LOCAL_MACHINE \софтваре\микрософт\\. Подраздел Нетфрамеворк\мда** (введите REG_SZ, значение 1) в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="72743-163">To enable MDAs, add the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA** subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="72743-164">Скопируйте следующий пример в текстовый файл с именем *мдаенабле. reg*. Откройте редактор реестра Windows (regedit. exe) и в меню **файл** выберите пункт **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="72743-164">Copy the following example into a text file named *MDAEnable.reg*. Open the Windows Registry Editor (RegEdit.exe), and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="72743-165">Выберите файл *мдаенабле. reg* , чтобы включить MDA на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="72743-165">Select the *MDAEnable.reg* file to enable MDAs on that computer.</span></span> <span data-ttu-id="72743-166">При установке подраздела в строковое значение **1** (а не значение DWORD, равное **1**) включает чтение параметров MDA из файла *ApplicationName. суффикс*. MDA. config.</span><span class="sxs-lookup"><span data-stu-id="72743-166">Setting the subkey to string value of **1** (not DWORD value of **1**) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="72743-167">Например, файл конфигурации MDA для блокнота будет называться Notepad. exe. MDA. config.</span><span class="sxs-lookup"><span data-stu-id="72743-167">For example, the MDA configuration file for Notepad would be named notepad.exe.mda.config.</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="72743-168">Если на компьютере в 64-разрядной операционной системе выполнянется 32-разрядное приложение, раздел помощника нужно задать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72743-168">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

<span data-ttu-id="72743-169">Дополнительные сведения см. в разделе [Параметры конфигурации, относящиеся к приложению](#application-specific-configuration-settings) .</span><span class="sxs-lookup"><span data-stu-id="72743-169">See [Application-Specific Configuration Settings](#application-specific-configuration-settings) for more information.</span></span> <span data-ttu-id="72743-170">Этот параметр реестра может быть перезаписан переменной среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-170">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="72743-171">Дополнительные сведения см. в разделе [переменная среды](#environment-variable) .</span><span class="sxs-lookup"><span data-stu-id="72743-171">See [Environment Variable](#environment-variable) for more information.</span></span>

<span data-ttu-id="72743-172">Чтобы отключить MDA, присвойте подразделу MDA значение **0** (ноль) с помощью редактора реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="72743-172">To disable MDAs, set the MDA subkey to **0** (zero) using the Windows Registry Editor.</span></span>

<span data-ttu-id="72743-173">По умолчанию некоторые помощники отладки управляемого кода включаются при запуске приложения, подключенного к отладчику, даже без добавления раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="72743-173">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="72743-174">Эти помощники можно отключить, запустив файл *мдадисабле. reg* , как описано выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="72743-174">You can disable these assistants by running the *MDADisable.reg* file as described earlier in this section.</span></span>

### <a name="environment-variable"></a><span data-ttu-id="72743-175">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="72743-175">Environment Variable</span></span>

<span data-ttu-id="72743-176">Активацией помощников также можно управлять с помощью переменной среды COMPLUS_MDA, которая переопределяет раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="72743-176">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="72743-177">Строка COMPLUS_MDA представляет собой разделенный точками с запятыми перечень имен помощников отладки управляемого кода или других специальных управляющих строк, составленный без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="72743-177">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="72743-178">При запуске под контролем управляемого или неуправляемого отладчика по умолчанию включается набор помощников.</span><span class="sxs-lookup"><span data-stu-id="72743-178">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="72743-179">Для этого необходимо неявным образом добавить разделенный точками с запятыми список помощников, которые включаются по умолчанию под контролем отладчиков, в начало значения переменной среды или раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="72743-179">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="72743-180">Специальные управляющие строки:</span><span class="sxs-lookup"><span data-stu-id="72743-180">The special control strings are the following:</span></span>

- <span data-ttu-id="72743-181">`0` — отключает все помощники.</span><span class="sxs-lookup"><span data-stu-id="72743-181">`0` - Deactivates all MDAs.</span></span>

- <span data-ttu-id="72743-182">`1` — считывает параметры помощника из файла *ИмяПриложения*.mda.config.</span><span class="sxs-lookup"><span data-stu-id="72743-182">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>

- <span data-ttu-id="72743-183">`managedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске управляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="72743-183">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>

- <span data-ttu-id="72743-184">`unmanagedDebugger` — явным образом активирует все помощники, которые активируются неявно при запуске неуправляемого исполняемого файла под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="72743-184">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>

<span data-ttu-id="72743-185">При наличии конфликтующих параметров более старые параметры переопределяются более новыми:</span><span class="sxs-lookup"><span data-stu-id="72743-185">If there are conflicting settings, the most recent settings override previous settings:</span></span>

- <span data-ttu-id="72743-186">`COMPLUS_MDA=0` отключает все помощники, включая те, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="72743-186">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="72743-187">`COMPLUS_MDA=gcUnmanagedToManaged` включает `gcUnmanagedToManaged` в дополнение к помощникам, которые неявно включаются под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="72743-187">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>

- <span data-ttu-id="72743-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` включает `gcUnmanagedToManaged`, но отключает те помощники, которые были бы неявно включены под контролем отладчика.</span><span class="sxs-lookup"><span data-stu-id="72743-188">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>

### <a name="application-specific-configuration-settings"></a><span data-ttu-id="72743-189">Параметры конфигурации для конкретного приложения</span><span class="sxs-lookup"><span data-stu-id="72743-189">Application-Specific Configuration Settings</span></span>

<span data-ttu-id="72743-190">Вы можете включать, отключать и настраивать некоторые помощники по отдельности в файле конфигурации помощников отладки управляемого кода для данного приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-190">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="72743-191">Чтобы разрешить использование файла конфигурации приложения для настройки помощников, необходимо задать раздел реестра или переменную среды COMPLUS_MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-191">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="72743-192">Файл конфигурации приложения обычно находится в одном каталоге с исполняемым файлом (EXE) приложения.</span><span class="sxs-lookup"><span data-stu-id="72743-192">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="72743-193">Имя файла имеет форму *applicationName*. MDA. config; Например, Notepad. exe. MDA. config. У помощников, включенных в файле конфигурации приложения, могут быть атрибуты или элементы, специально предназначенные для управления поведением этого помощника.</span><span class="sxs-lookup"><span data-stu-id="72743-193">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span>

<span data-ttu-id="72743-194">В следующем примере показано, как включить и настроить [упаковку](marshaling-mda.md):</span><span class="sxs-lookup"><span data-stu-id="72743-194">The following example shows how to enable and configure the [marshaling](marshaling-mda.md):</span></span>

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

<span data-ttu-id="72743-195">Помощник отладки управляемого кода `Marshaling` выдает информацию об управляемом типе, который маршалируется в неуправляемый тип для каждого перехода между управляемым и неуправляемым кодом в приложении.</span><span class="sxs-lookup"><span data-stu-id="72743-195">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="72743-196">`Marshaling` MDA также может фильтровать имена методов и полей структуры, предоставляемых в дочерних элементах **месодфилтер** и **фиелдфилтер** соответственно.</span><span class="sxs-lookup"><span data-stu-id="72743-196">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the **methodFilter** and **fieldFilter** child elements, respectively.</span></span>

<span data-ttu-id="72743-197">В следующем примере показано, как включить несколько MDA с помощью параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72743-197">The following example shows how to enable multiple MDAs by using their default settings:</span></span>

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
> <span data-ttu-id="72743-198">При указании нескольких помощников в файле конфигурации их следует перечислять в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="72743-198">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="72743-199">Например, если вы хотите включить помощники `virtualCERCall` и `invalidCERCall`, необходимо добавить запись `<invalidCERCall />` перед записью `<virtualCERCall />`.</span><span class="sxs-lookup"><span data-stu-id="72743-199">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="72743-200">Если записи расположены не в алфавитном порядке, отображается сообщение о необработанном исключении недопустимого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="72743-200">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>

## <a name="mda-exceptions"></a><span data-ttu-id="72743-201">Исключения MDA</span><span class="sxs-lookup"><span data-stu-id="72743-201">MDA exceptions</span></span>

<span data-ttu-id="72743-202">Если MDA включен, он активен даже в том случае, если код не выполняется в отладчике.</span><span class="sxs-lookup"><span data-stu-id="72743-202">When an MDA is enabled, it's active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="72743-203">Если событие помощника отладки управляемого кода возникает при отсутствии отладчика, сообщений события выводится в диалоговом окне необработанного исключения, хотя оно и не является необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="72743-203">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="72743-204">Чтобы предотвратить появление диалогового окна, удаляйте параметр, отвечающий за включение помощника, когда ваш код не выполняется в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="72743-204">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>

<span data-ttu-id="72743-205">Когда код выполняется в интегрированной среде разработки Visual Studio (IDE), можно избежать диалогового окна исключения, которое отображается для конкретных событий MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-205">When your code executes in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="72743-206">Для этого в меню **Отладка** выберите пункт **параметры исключений** **Windows** > .</span><span class="sxs-lookup"><span data-stu-id="72743-206">To do that, on the **Debug** menu, choose **Windows** > **Exception Settings**.</span></span> <span data-ttu-id="72743-207">В окне **параметры исключений** разверните список **помощники по отладке управляемого** кода, а затем снимите флажок **прерывать при возникновении** для отдельного MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-207">In the **Exception Settings** window, expand the **Managed Debugging Assistants** list, and then clear the **Break When Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="72743-208">Это диалоговое окно также можно использовать, чтобы *включить* отображение диалоговых окон исключений MDA.</span><span class="sxs-lookup"><span data-stu-id="72743-208">You can also use this dialog box to *enable* the display of MDA exception dialog boxes.</span></span>

## <a name="mda-output"></a><span data-ttu-id="72743-209">Выходные данные помощников</span><span class="sxs-lookup"><span data-stu-id="72743-209">MDA Output</span></span>

<span data-ttu-id="72743-210">Выходные данные MDA похожи на приведенный ниже пример, который показывает выходные данные `PInvokeStackImbalance` MDA:</span><span class="sxs-lookup"><span data-stu-id="72743-210">MDA output is similar to the following example, which shows the output from the `PInvokeStackImbalance` MDA:</span></span>

<span data-ttu-id="72743-211">**Вызов функции PInvoke "Мдатест! Мдатест. Program:: StdCall ' имеет несбалансированный стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**</span><span class="sxs-lookup"><span data-stu-id="72743-211">**A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="see-also"></a><span data-ttu-id="72743-212">См. также:</span><span class="sxs-lookup"><span data-stu-id="72743-212">See also</span></span>

- [<span data-ttu-id="72743-213">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="72743-213">Debugging, Tracing, and Profiling</span></span>](index.md)
