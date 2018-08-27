---
title: Функция CorBindToRuntimeEx
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 553bbd79241292e1fa3b4fe718bda391191a10ae
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935326"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="14439-102">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="14439-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="14439-103">Позволяет неуправляемым основным приложениям загружать в процесс общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="14439-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="14439-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) и `CorBindToRuntimeEx` функции выполняют та же операция, но `CorBindToRuntimeEx` функция позволяет задавать флаги для определения поведения этой СРЕДЫ.</span><span class="sxs-lookup"><span data-stu-id="14439-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="14439-105">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14439-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
 <span data-ttu-id="14439-106">Эта функция принимает набор параметров, которые позволяют ведущему приложению сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="14439-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
-   <span data-ttu-id="14439-107">Укажите версию среды выполнения, которые будут загружены.</span><span class="sxs-lookup"><span data-stu-id="14439-107">Specify the version of the runtime that will be loaded.</span></span>  
  
-   <span data-ttu-id="14439-108">Указывает, следует ли загружать сборки сервера или рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="14439-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
-   <span data-ttu-id="14439-109">Контролировать, выполняется ли параллельная сборка мусора или непараллельной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="14439-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14439-110">Параллельная сборка мусора не поддерживается в приложениях, выполняемых WOW64 x86 эмулятора на 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64).</span><span class="sxs-lookup"><span data-stu-id="14439-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="14439-111">Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows, см. в разделе [под управлением 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="14439-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
-   <span data-ttu-id="14439-112">Контролировать, загружаются ли сборки как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="14439-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
-   <span data-ttu-id="14439-113">Получить указатель интерфейса на [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) , можно использовать для задания дополнительных параметров для настройки экземпляра среды CLR перед его запуском.</span><span class="sxs-lookup"><span data-stu-id="14439-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14439-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14439-114">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14439-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="14439-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="14439-116">[in] Строка, описывающая версию среды CLR, вы хотите загрузить.</span><span class="sxs-lookup"><span data-stu-id="14439-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="14439-117">Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="14439-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="14439-118">Строка, передаваемая как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).</span><span class="sxs-lookup"><span data-stu-id="14439-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="14439-119">В некоторых версиях среды CLR, устанавливаются вместе с инструкцию политики, которая указывает совместимости с предыдущими версиями среды CLR.</span><span class="sxs-lookup"><span data-stu-id="14439-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="14439-120">По умолчанию оболочка загрузки оценивает `pwszVersion` от операторов политик и загружает последнюю версию среды выполнения, совместима с запрашиваемой.</span><span class="sxs-lookup"><span data-stu-id="14439-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="14439-121">Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точной версии, указанной в `pwszVersion` , передав значение `STARTUP_LOADER_SAFEMODE` для `startupFlags` параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="14439-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="14439-122">Если вызывающая сторона задает значение null для `pwszVersion`, `CorBindToRuntimeEx` определяет набор установленных сред выполнения, номера версий ниже, чем среда выполнения .NET Framework 4 и загружает последнюю версию среды выполнения на основе этого набора.</span><span class="sxs-lookup"><span data-stu-id="14439-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="14439-123">Не загрузит .NET Framework 4 или более поздней версии и завершается ошибкой, если установлены более ранние версии.</span><span class="sxs-lookup"><span data-stu-id="14439-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="14439-124">Обратите внимание, что передача null предоставляет узлу не управляет, по которому загружается версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14439-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="14439-125">Несмотря на то, что этот подход может быть полезным в некоторых сценариях, настоятельно рекомендуется указывать определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="14439-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="14439-126">[in] Строковое значение, указывающее, следует ли загружать на сервере или рабочей станции сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="14439-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="14439-127">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="14439-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="14439-128">Построение сервера оптимизирован так, чтобы воспользоваться преимуществами нескольких процессоров для сборки мусора и построение рабочей станции оптимизировано для клиентских приложений на однопроцессорном компьютере.</span><span class="sxs-lookup"><span data-stu-id="14439-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="14439-129">Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="14439-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="14439-130">При выполнении на однопроцессорном компьютере всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` присваивается `svr`.</span><span class="sxs-lookup"><span data-stu-id="14439-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="14439-131">Тем не менее если `pwszBuildFlavor` присваивается `svr` и указывается параллельной сборки мусора (см. в описании `startupFlags` параметр), загружается построение сервера.</span><span class="sxs-lookup"><span data-stu-id="14439-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="14439-132">[in] Сочетание значений [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="14439-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="14439-133">Эти флаги позволяют управлять параллельной сборки мусора, независимый от домена код и поведение `pwszVersion` параметра.</span><span class="sxs-lookup"><span data-stu-id="14439-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="14439-134">Значение по умолчанию — один домен, если не установлен флаг.</span><span class="sxs-lookup"><span data-stu-id="14439-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="14439-135">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="14439-135">The following values are valid:</span></span>  
  
-   `STARTUP_CONCURRENT_GC`  
  
-   `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
-   `STARTUP_LOADER_SAFEMODE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_LOADER_SETPREFERENCE`  
  
-   `STARTUP_SERVER_GC`  
  
-   `STARTUP_HOARD_GC_VM`  
  
-   `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
-   `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="14439-136">Описание этих флагов, см. в разделе [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="14439-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="14439-137">[in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="14439-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="14439-138">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="14439-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="14439-139">[in] `IID` Запрошенного интерфейса из `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="14439-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="14439-140">Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="14439-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="14439-141">[out] Указатель на возвращенный интерфейс `riid`.</span><span class="sxs-lookup"><span data-stu-id="14439-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14439-142">Примечания</span><span class="sxs-lookup"><span data-stu-id="14439-142">Remarks</span></span>  
 <span data-ttu-id="14439-143">Если `pwszVersion` указывает версию среды выполнения, которая не существует, `CorBindToRuntimeEx` возвращает HRESULT со значением CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="14439-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="14439-144">Контекст выполнения и поток удостоверения Windows</span><span class="sxs-lookup"><span data-stu-id="14439-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="14439-145">В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="14439-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="14439-146">В версии 2.0 среды CLR <xref:System.Threading.ExecutionContext> объект включает некоторые сведения о текущем потоке и проходит через все асинхронные точки, но не через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="14439-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="14439-147">Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объекта, также проходит через все асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="14439-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="14439-148">Таким образом текущий олицетворения в потоке, если таковой имеется, он проходит.</span><span class="sxs-lookup"><span data-stu-id="14439-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="14439-149">Можно изменить последовательность из двух способов:</span><span class="sxs-lookup"><span data-stu-id="14439-149">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="14439-150">Изменив <xref:System.Threading.ExecutionContext> параметры потока на основе отдельного потока (см. в разделе <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методов).</span><span class="sxs-lookup"><span data-stu-id="14439-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="14439-151">Изменив режим по умолчанию процесс в режиме совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через все асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> параметры в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="14439-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="14439-152">Как изменить режим по умолчанию зависит от того, используются ли управляемый исполняемый файл или неуправляемый интерфейс размещения загружать среду CLR.</span><span class="sxs-lookup"><span data-stu-id="14439-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="14439-153">Для управляемых исполняемых файлов, необходимо задать `enabled` атрибут [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) элемент `true`.</span><span class="sxs-lookup"><span data-stu-id="14439-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="14439-154">Неуправляемые интерфейсы размещения, задать `STARTUP_LEGACY_IMPERSONATION` флаг в `startupFlags` параметра при вызове `CorBindToRuntimeEx` функции.</span><span class="sxs-lookup"><span data-stu-id="14439-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="14439-155">Режим совместимости версии 1 применяется ко всему процессу и для всех доменов приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="14439-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14439-156">Требования</span><span class="sxs-lookup"><span data-stu-id="14439-156">Requirements</span></span>  
 <span data-ttu-id="14439-157">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14439-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14439-158">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14439-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14439-159">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14439-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14439-160">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14439-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14439-161">См. также</span><span class="sxs-lookup"><span data-stu-id="14439-161">See Also</span></span>  
 [<span data-ttu-id="14439-162">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="14439-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="14439-163">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="14439-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="14439-164">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="14439-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="14439-165">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="14439-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="14439-166">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="14439-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="14439-167">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="14439-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
