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
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176504"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="c8895-102">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="c8895-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="c8895-103">Позволяет неуправляемым хостам загружать время выполнения общего языка (CLR) в процесс.</span><span class="sxs-lookup"><span data-stu-id="c8895-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="c8895-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) и `CorBindToRuntimeEx` функции выполняют ту `CorBindToRuntimeEx` же операцию, но функция позволяет установить флаги, чтобы указать поведение CLR.</span><span class="sxs-lookup"><span data-stu-id="c8895-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="c8895-105">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="c8895-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="c8895-106">Эта функция выполняет набор параметров, которые позволяют хосту сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c8895-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="c8895-107">Укажите версию времени выполнения, которая будет загружена.</span><span class="sxs-lookup"><span data-stu-id="c8895-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="c8895-108">Укажите, следует ли загрузить сборку сервера или рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="c8895-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="c8895-109">Контролируйте, осуществляется ли параллельный сбор мусора или непараллельный сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="c8895-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8895-110">Параллельный сбор мусора не поддерживается в приложениях под управлением эмулятора WOW64 x86 на 64-битных системах, реализуемых в архитектуре Intel Itanium (ранее именуемой IA-64).</span><span class="sxs-lookup"><span data-stu-id="c8895-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="c8895-111">Для получения дополнительной информации об использовании WOW64 на 64-битных системах Windows [см.](/windows/desktop/WinProg64/running-32-bit-applications)</span><span class="sxs-lookup"><span data-stu-id="c8895-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="c8895-112">Контролируйте, загружаются ли сборки как нейтральные домены.</span><span class="sxs-lookup"><span data-stu-id="c8895-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="c8895-113">Получите указатель интерфейса на [ICorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) который можно использовать для настройки экземпляра CLR до его запуска.</span><span class="sxs-lookup"><span data-stu-id="c8895-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8895-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8895-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,
    [in]  LPCWSTR      pwszBuildFlavor,
    [in]  DWORD        startupFlags,
    [in]  REFCLSID     rclsid,
    [in]  REFIID       riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8895-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8895-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="c8895-116">(в) Строка, описывающая версию CLR, которая вы хотите загрузить.</span><span class="sxs-lookup"><span data-stu-id="c8895-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="c8895-117">Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="c8895-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="c8895-118">Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="c8895-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="c8895-119">Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR.</span><span class="sxs-lookup"><span data-stu-id="c8895-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="c8895-120">По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="c8895-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="c8895-121">Хост может заставить shim пропустить оценку `pwszVersion` политики и `STARTUP_LOADER_SAFEMODE` загрузить `startupFlags` точную версию, указанную в, передавая значение для параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c8895-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="c8895-122">Если абонент указывает null for, `pwszVersion` `CorBindToRuntimeEx` определяет набор установленных времен выполнения, номера версий которых ниже, чем время выполнения .NET Framework 4, и загружает последнюю версию времени выполнения из этого набора.</span><span class="sxs-lookup"><span data-stu-id="c8895-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="c8895-123">Он не будет загружать сяррамки .NET 4 или позже, и выходит из строя, если не будет установлена более ранняя версия.</span><span class="sxs-lookup"><span data-stu-id="c8895-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="c8895-124">Обратите внимание, что прохождение нулевой не дает хосту никакого контроля над тем, какая версия времени выполнения загружается.</span><span class="sxs-lookup"><span data-stu-id="c8895-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="c8895-125">Хотя этот подход может быть уместным в некоторых сценариях, настоятельно рекомендуется, чтобы ухост поставлял определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="c8895-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="c8895-126">(в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR.</span><span class="sxs-lookup"><span data-stu-id="c8895-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="c8895-127">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="c8895-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="c8895-128">Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.</span><span class="sxs-lookup"><span data-stu-id="c8895-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="c8895-129">Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается.</span><span class="sxs-lookup"><span data-stu-id="c8895-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="c8895-130">При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr`</span><span class="sxs-lookup"><span data-stu-id="c8895-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="c8895-131">Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `startupFlags` указан (см. описание параметра), сборка сервера загружается.</span><span class="sxs-lookup"><span data-stu-id="c8895-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="c8895-132">(в) Сочетание значений [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="c8895-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="c8895-133">Эти флаги контролируют параллельный сбор мусора, нейтральный код домена и поведение `pwszVersion` параметра.</span><span class="sxs-lookup"><span data-stu-id="c8895-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="c8895-134">По умолчанию один домен, если флаг не установлен.</span><span class="sxs-lookup"><span data-stu-id="c8895-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="c8895-135">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c8895-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="c8895-136">Описания этих флагов смотрите [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="c8895-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="c8895-137">(в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)</span><span class="sxs-lookup"><span data-stu-id="c8895-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="c8895-138">Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="c8895-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="c8895-139">(в) Запрашиваемый `IID` интерфейс `rclsid`от .</span><span class="sxs-lookup"><span data-stu-id="c8895-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="c8895-140">Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="c8895-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="c8895-141">(ваут) Возвращается указатель `riid`интерфейса к .</span><span class="sxs-lookup"><span data-stu-id="c8895-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8895-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8895-142">Remarks</span></span>  
 <span data-ttu-id="c8895-143">Если `pwszVersion` указывается версия времени выполнения, которая `CorBindToRuntimeEx` не существует, возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="c8895-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="c8895-144">Контекст выполнения и поток идентификации Windows</span><span class="sxs-lookup"><span data-stu-id="c8895-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="c8895-145">В версии 1 CLR <xref:System.Security.Principal.WindowsIdentity> объект не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймер.</span><span class="sxs-lookup"><span data-stu-id="c8895-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="c8895-146">В версии 2.0 CLR <xref:System.Threading.ExecutionContext> объект обертывает некоторую информацию о исполняемый в настоящее время потоке и перетекает в любую асинхронную точку, но не через границы доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="c8895-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="c8895-147">Аналогичным образом, <xref:System.Security.Principal.WindowsIdentity> объект также течет через любую асинхронную точку.</span><span class="sxs-lookup"><span data-stu-id="c8895-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="c8895-148">Таким образом, текущее олицетворение на потоке, если таковые имеется, течет тоже.</span><span class="sxs-lookup"><span data-stu-id="c8895-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="c8895-149">Вы можете изменить поток двумя способами:</span><span class="sxs-lookup"><span data-stu-id="c8895-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="c8895-150">Изменяя <xref:System.Threading.ExecutionContext> настройки для подавления потока на основе потока <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A>(см. , и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методы).</span><span class="sxs-lookup"><span data-stu-id="c8895-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="c8895-151">Изменяя режим по умолчанию процесса на режим <xref:System.Security.Principal.WindowsIdentity> совместимости версии 1, где объект не <xref:System.Threading.ExecutionContext> проходит через какую-либо асинхронную точку, независимо от настроек текущего потока.</span><span class="sxs-lookup"><span data-stu-id="c8895-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="c8895-152">Как изменить режим по умолчанию зависит от того, используете ли вы управляемый исполняемый или неуправляемый интерфейс хостинга для загрузки CLR:</span><span class="sxs-lookup"><span data-stu-id="c8895-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="c8895-153">Для управляемых исполнителей необходимо установить `enabled` атрибут [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) `true`элемент.</span><span class="sxs-lookup"><span data-stu-id="c8895-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="c8895-154">Для неуправляемых интерфейсов `STARTUP_LEGACY_IMPERSONATION` хостинга `startupFlags` установите флаг `CorBindToRuntimeEx` в параметре при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="c8895-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="c8895-155">Режим совместимости версии 1 применяется ко всему процессу и ко всем доменам приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="c8895-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8895-156">Требования</span><span class="sxs-lookup"><span data-stu-id="c8895-156">Requirements</span></span>  
 <span data-ttu-id="c8895-157">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8895-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8895-158">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8895-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8895-159">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8895-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8895-160">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8895-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8895-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c8895-161">See also</span></span>

- [<span data-ttu-id="c8895-162">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="c8895-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="c8895-163">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="c8895-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="c8895-164">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="c8895-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="c8895-165">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c8895-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="c8895-166">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c8895-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="c8895-167">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c8895-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
