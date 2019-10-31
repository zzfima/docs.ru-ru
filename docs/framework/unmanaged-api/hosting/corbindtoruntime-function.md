---
title: Функция CorBindToRuntime
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 9d4b8bb7d5b3da15f665849c8d18c3a10dbe600b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138312"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="6209e-102">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="6209e-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="6209e-103">Позволяет неуправляемым узлам загружать среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="6209e-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="6209e-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6209e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6209e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6209e-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6209e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6209e-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="6209e-107">окне Строка, описывающая версию среды CLR, которую требуется загрузить.</span><span class="sxs-lookup"><span data-stu-id="6209e-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="6209e-108">Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *основной. дополнительный. сборка. Редакция*.</span><span class="sxs-lookup"><span data-stu-id="6209e-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="6209e-109">Строка, передаваемая как `pwszVersion`, должна начинаться с символа "v", за которым следуют первые три части номера версии (например, "v 1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="6209e-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="6209e-110">Некоторые версии среды CLR устанавливаются с инструкцией политики, которая определяет совместимость с предыдущими версиями среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6209e-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="6209e-111">По умолчанию оболочка запуска проверяет `pwszVersion` в соответствии с инструкциями политики и загружает последнюю версию среды выполнения, совместимую с запрашиваемой версией.</span><span class="sxs-lookup"><span data-stu-id="6209e-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="6209e-112">Узел может заставить оболочку пропускать вычисление политики и загружать точную версию, указанную в `pwszVersion`, передав значение `STARTUP_LOADER_SAFEMODE` для параметра `flags`, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6209e-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="6209e-113">Если вызывающий объект указывает значение NULL для `pwszVersion`, загружается последняя версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6209e-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="6209e-114">Передача значения NULL позволяет узлу не контролировать, какая версия среды выполнения загружена.</span><span class="sxs-lookup"><span data-stu-id="6209e-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="6209e-115">Хотя такой подход может быть приемлемым в некоторых сценариях, настоятельно рекомендуется, чтобы узел предоставил определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="6209e-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="6209e-116">окне Строка, указывающая, загружать ли сервер или рабочую станцию сборку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6209e-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="6209e-117">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="6209e-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="6209e-118">Сборка сервера оптимизирована для использования нескольких процессоров для сборок мусора, а сборка рабочей станции оптимизирована для клиентских приложений, работающих на однопроцессорном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6209e-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="6209e-119">Если `pwszBuildFlavor` имеет значение null, загружается сборка рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="6209e-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="6209e-120">При запуске на однопроцессорном компьютере сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` имеет значение `svr`.</span><span class="sxs-lookup"><span data-stu-id="6209e-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="6209e-121">Однако если `pwszBuildFlavor` имеет значение `svr` и задана параллельная сборка мусора (см. Описание параметра `flags`), то загружается серверная сборка.</span><span class="sxs-lookup"><span data-stu-id="6209e-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="6209e-122">окне `CLSID` компонентного класса, реализующего интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6209e-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="6209e-123">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="6209e-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="6209e-124">окне `IID` запрашиваемого интерфейса из `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="6209e-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="6209e-125">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="6209e-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="6209e-126">заполняет Возвращаемый указатель интерфейса на `riid`.</span><span class="sxs-lookup"><span data-stu-id="6209e-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6209e-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="6209e-127">Remarks</span></span>  
 <span data-ttu-id="6209e-128">Если `pwszVersion` указывает несуществующую версию среды выполнения, `CorBindToRuntimeEx` возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="6209e-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="6209e-129">Контекст выполнения и поток удостоверения Windows</span><span class="sxs-lookup"><span data-stu-id="6209e-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="6209e-130">В версии 1 среды CLR объект <xref:System.Security.Principal.WindowsIdentity> не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="6209e-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="6209e-131">В версии 2,0 среды CLR объект <xref:System.Threading.ExecutionContext> заключает некоторые сведения о выполняемом в данный момент потоке и передает его через любую асинхронную точку, но не через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="6209e-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="6209e-132">Аналогичным образом объект <xref:System.Security.Principal.WindowsIdentity> также проходит через любую асинхронную точку.</span><span class="sxs-lookup"><span data-stu-id="6209e-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="6209e-133">Таким образом, текущее олицетворение в потоке, если таковое имеется, также проходит.</span><span class="sxs-lookup"><span data-stu-id="6209e-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="6209e-134">Изменить последовательность можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="6209e-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="6209e-135">Изменяя параметры <xref:System.Threading.ExecutionContext> для подавления потока на основе потока (см. методы <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).</span><span class="sxs-lookup"><span data-stu-id="6209e-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="6209e-136">Изменив режим обработки по умолчанию на режим совместимости версии 1, где объект <xref:System.Security.Principal.WindowsIdentity> не пополняется по какой бы то ни было асинхронной точке, независимо от параметров <xref:System.Threading.ExecutionContext> в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="6209e-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="6209e-137">Изменение режима по умолчанию зависит от того, используется ли управляемый исполняемый файл или неуправляемый интерфейс размещения для загрузки среды CLR:</span><span class="sxs-lookup"><span data-stu-id="6209e-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="6209e-138">Для управляемых исполняемых файлов необходимо задать атрибут `enabled` элемента [\<легациимперсонатионполици >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) для `true`.</span><span class="sxs-lookup"><span data-stu-id="6209e-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="6209e-139">Для неуправляемых интерфейсов размещения установите флаг `STARTUP_LEGACY_IMPERSONATION` в параметре `flags` при вызове функции `CorBindToRuntimeEx`.</span><span class="sxs-lookup"><span data-stu-id="6209e-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="6209e-140">Режим совместимости версии 1 применяется ко всему процессу и всем доменам приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="6209e-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6209e-141">Заметки</span><span class="sxs-lookup"><span data-stu-id="6209e-141">Remarks</span></span>  
 <span data-ttu-id="6209e-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и `CorBindToRuntime` выполняют одну и ту же операцию, но функция `CorBindToRuntimeEx` позволяет устанавливать флаги для указания поведения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6209e-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6209e-143">Требования</span><span class="sxs-lookup"><span data-stu-id="6209e-143">Requirements</span></span>  
 <span data-ttu-id="6209e-144">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6209e-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6209e-145">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6209e-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6209e-146">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6209e-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6209e-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6209e-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6209e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="6209e-148">See also</span></span>

- [<span data-ttu-id="6209e-149">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="6209e-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="6209e-150">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="6209e-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="6209e-151">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="6209e-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="6209e-152">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6209e-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="6209e-153">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6209e-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="6209e-154">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="6209e-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
