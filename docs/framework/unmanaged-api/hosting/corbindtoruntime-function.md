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
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176517"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="66869-102">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="66869-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="66869-103">Позволяет неуправляемым хостам загружать время выполнения общего языка (CLR) в процесс.</span><span class="sxs-lookup"><span data-stu-id="66869-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="66869-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="66869-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66869-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66869-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66869-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="66869-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="66869-107">(в) Строка, описывающая версию CLR, которая вы хотите загрузить.</span><span class="sxs-lookup"><span data-stu-id="66869-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="66869-108">Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="66869-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="66869-109">Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="66869-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="66869-110">Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR.</span><span class="sxs-lookup"><span data-stu-id="66869-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="66869-111">По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="66869-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="66869-112">Хост может заставить shim пропустить оценку `pwszVersion` политики и `STARTUP_LOADER_SAFEMODE` загрузить `flags` точную версию, указанную в, передавая значение для параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="66869-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="66869-113">Если абонент указывает нулевую `pwszVersion`для, последняя версия времени выполнения загружается.</span><span class="sxs-lookup"><span data-stu-id="66869-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="66869-114">Прохождение null не дает хостам никакого контроля над тем, какая версия времени выполнения загружается.</span><span class="sxs-lookup"><span data-stu-id="66869-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="66869-115">Хотя этот подход может быть уместным в некоторых сценариях, настоятельно рекомендуется, чтобы ухост поставлял определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="66869-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="66869-116">(в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR.</span><span class="sxs-lookup"><span data-stu-id="66869-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="66869-117">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="66869-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="66869-118">Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.</span><span class="sxs-lookup"><span data-stu-id="66869-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="66869-119">Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается.</span><span class="sxs-lookup"><span data-stu-id="66869-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="66869-120">При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr`</span><span class="sxs-lookup"><span data-stu-id="66869-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="66869-121">Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `flags` указан (см. описание параметра), сборка сервера загружается.</span><span class="sxs-lookup"><span data-stu-id="66869-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="66869-122">(в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)</span><span class="sxs-lookup"><span data-stu-id="66869-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="66869-123">Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="66869-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="66869-124">(в) Запрашиваемый `IID` интерфейс `rclsid`от .</span><span class="sxs-lookup"><span data-stu-id="66869-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="66869-125">Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="66869-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="66869-126">(ваут) Возвращается указатель `riid`интерфейса к .</span><span class="sxs-lookup"><span data-stu-id="66869-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66869-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="66869-127">Remarks</span></span>  
 <span data-ttu-id="66869-128">Если `pwszVersion` указывается версия времени выполнения, которая `CorBindToRuntimeEx` не существует, возвращает значение HRESULT CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="66869-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="66869-129">Контекст выполнения и поток идентификации Windows</span><span class="sxs-lookup"><span data-stu-id="66869-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="66869-130">В версии 1 CLR <xref:System.Security.Principal.WindowsIdentity> объект не перетекает через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймер.</span><span class="sxs-lookup"><span data-stu-id="66869-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="66869-131">В версии 2.0 CLR <xref:System.Threading.ExecutionContext> объект обертывает некоторую информацию о исполняемый в настоящее время потоке и перетекает в любую асинхронную точку, но не через границы доменов приложения.</span><span class="sxs-lookup"><span data-stu-id="66869-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="66869-132">Аналогичным образом, <xref:System.Security.Principal.WindowsIdentity> объект также течет через любую асинхронную точку.</span><span class="sxs-lookup"><span data-stu-id="66869-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="66869-133">Таким образом, текущее олицетворение на потоке, если таковые имеется, течет тоже.</span><span class="sxs-lookup"><span data-stu-id="66869-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="66869-134">Вы можете изменить поток двумя способами:</span><span class="sxs-lookup"><span data-stu-id="66869-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="66869-135">Изменяя <xref:System.Threading.ExecutionContext> настройки для подавления потока на основе потока <xref:System.Threading.ExecutionContext.SuppressFlow%2A> <xref:System.Security.SecurityContext.SuppressFlow%2A>(см. , и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методы).</span><span class="sxs-lookup"><span data-stu-id="66869-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="66869-136">Изменяя режим по умолчанию процесса на режим <xref:System.Security.Principal.WindowsIdentity> совместимости версии 1, где объект не <xref:System.Threading.ExecutionContext> проходит через какую-либо асинхронную точку, независимо от настроек текущего потока.</span><span class="sxs-lookup"><span data-stu-id="66869-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="66869-137">Как изменить режим по умолчанию зависит от того, используете ли вы управляемый исполняемый или неуправляемый интерфейс хостинга для загрузки CLR:</span><span class="sxs-lookup"><span data-stu-id="66869-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="66869-138">Для управляемых исполнителей необходимо установить `enabled` атрибут [ \<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) `true`элемент.</span><span class="sxs-lookup"><span data-stu-id="66869-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="66869-139">Для неуправляемых интерфейсов `STARTUP_LEGACY_IMPERSONATION` хостинга `flags` установите флаг `CorBindToRuntimeEx` в параметре при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="66869-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="66869-140">Режим совместимости версии 1 применяется ко всему процессу и ко всем доменам приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="66869-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66869-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="66869-141">Remarks</span></span>  
 <span data-ttu-id="66869-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime` и выполнять ту же `CorBindToRuntimeEx` операцию, но функция позволяет установить флаги, чтобы указать поведение CLR.</span><span class="sxs-lookup"><span data-stu-id="66869-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66869-143">Требования</span><span class="sxs-lookup"><span data-stu-id="66869-143">Requirements</span></span>  
 <span data-ttu-id="66869-144">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66869-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66869-145">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66869-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66869-146">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66869-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66869-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66869-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66869-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66869-148">See also</span></span>

- [<span data-ttu-id="66869-149">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="66869-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="66869-150">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="66869-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="66869-151">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="66869-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="66869-152">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="66869-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="66869-153">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="66869-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="66869-154">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="66869-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
