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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b9b17c1457a920aa3e05f5fd839e6ffdc0c6fee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144369"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="001f8-102">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="001f8-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="001f8-103">Позволяет неуправляемым основным приложениям загружать в процесс общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="001f8-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="001f8-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="001f8-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="001f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="001f8-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="001f8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="001f8-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="001f8-107">[in] Строка, описывающая версию среды CLR, вы хотите загрузить.</span><span class="sxs-lookup"><span data-stu-id="001f8-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="001f8-108">Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="001f8-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="001f8-109">Строка, передаваемая как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).</span><span class="sxs-lookup"><span data-stu-id="001f8-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="001f8-110">В некоторых версиях среды CLR, устанавливаются вместе с инструкцию политики, которая указывает совместимости с предыдущими версиями среды CLR.</span><span class="sxs-lookup"><span data-stu-id="001f8-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="001f8-111">По умолчанию оболочка загрузки оценивает `pwszVersion` от операторов политик и загружает последнюю версию среды выполнения, совместима с запрашиваемой.</span><span class="sxs-lookup"><span data-stu-id="001f8-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="001f8-112">Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точной версии, указанной в `pwszVersion` , передав значение `STARTUP_LOADER_SAFEMODE` для `flags` параметра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="001f8-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="001f8-113">Если вызывающая сторона задает значение null для `pwszVersion`, загружается последняя версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="001f8-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="001f8-114">Передачу значений null дает узлу не управляет, по которому загружается версия среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="001f8-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="001f8-115">Несмотря на то, что этот подход может быть полезным в некоторых сценариях, настоятельно рекомендуется указывать определенную версию для загрузки.</span><span class="sxs-lookup"><span data-stu-id="001f8-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="001f8-116">[in] Строковое значение, указывающее, следует ли загружать на сервере или рабочей станции сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="001f8-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="001f8-117">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="001f8-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="001f8-118">Построение сервера оптимизирован так, чтобы воспользоваться преимуществами нескольких процессоров для сборки мусора и построение рабочей станции оптимизировано для клиентских приложений на однопроцессорном компьютере.</span><span class="sxs-lookup"><span data-stu-id="001f8-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="001f8-119">Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="001f8-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="001f8-120">При выполнении на однопроцессорном компьютере всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` присваивается `svr`.</span><span class="sxs-lookup"><span data-stu-id="001f8-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="001f8-121">Тем не менее если `pwszBuildFlavor` присваивается `svr` и указывается параллельной сборки мусора (см. в описании `flags` параметр), загружается построение сервера.</span><span class="sxs-lookup"><span data-stu-id="001f8-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="001f8-122">[in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="001f8-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="001f8-123">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="001f8-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="001f8-124">[in] `IID` Запрошенного интерфейса из `rclsid`.</span><span class="sxs-lookup"><span data-stu-id="001f8-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="001f8-125">Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="001f8-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="001f8-126">[out] Указатель на возвращенный интерфейс `riid`.</span><span class="sxs-lookup"><span data-stu-id="001f8-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="001f8-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="001f8-127">Remarks</span></span>  
 <span data-ttu-id="001f8-128">Если `pwszVersion` указывает версию среды выполнения, которая не существует, `CorBindToRuntimeEx` возвращает HRESULT со значением CLR_E_SHIM_RUNTIMELOAD.</span><span class="sxs-lookup"><span data-stu-id="001f8-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="001f8-129">Контекст выполнения и поток удостоверения Windows</span><span class="sxs-lookup"><span data-stu-id="001f8-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="001f8-130">В версии 1 среды CLR <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через асинхронные точки, такие как новые потоки, пулы потоков или обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="001f8-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="001f8-131">В версии 2.0 среды CLR <xref:System.Threading.ExecutionContext> объект включает некоторые сведения о текущем потоке и проходит через все асинхронные точки, но не через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="001f8-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="001f8-132">Аналогичным образом <xref:System.Security.Principal.WindowsIdentity> объекта, также проходит через все асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="001f8-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="001f8-133">Таким образом текущий олицетворения в потоке, если таковой имеется, он проходит.</span><span class="sxs-lookup"><span data-stu-id="001f8-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="001f8-134">Можно изменить последовательность из двух способов:</span><span class="sxs-lookup"><span data-stu-id="001f8-134">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="001f8-135">Изменив <xref:System.Threading.ExecutionContext> параметры потока на основе отдельного потока (см. в разделе <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, и <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> методов).</span><span class="sxs-lookup"><span data-stu-id="001f8-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="001f8-136">Изменив режим по умолчанию процесс в режиме совместимости версии 1, где <xref:System.Security.Principal.WindowsIdentity> объекта не проходит через все асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> параметры в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="001f8-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="001f8-137">Как изменить режим по умолчанию зависит от того, используются ли управляемый исполняемый файл или неуправляемый интерфейс размещения загружать среду CLR.</span><span class="sxs-lookup"><span data-stu-id="001f8-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="001f8-138">Для управляемых исполняемых файлов, необходимо задать `enabled` атрибут [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) элемент `true`.</span><span class="sxs-lookup"><span data-stu-id="001f8-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="001f8-139">Неуправляемые интерфейсы размещения, задать `STARTUP_LEGACY_IMPERSONATION` флаг в `flags` параметра при вызове `CorBindToRuntimeEx` функции.</span><span class="sxs-lookup"><span data-stu-id="001f8-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="001f8-140">Режим совместимости версии 1 применяется ко всему процессу и для всех доменов приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="001f8-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="001f8-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="001f8-141">Remarks</span></span>  
 <span data-ttu-id="001f8-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и `CorBindToRuntime` выполнить те же операции, но `CorBindToRuntimeEx` функция позволяет задавать флаги для определения поведения этой СРЕДЫ.</span><span class="sxs-lookup"><span data-stu-id="001f8-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="001f8-143">Требования</span><span class="sxs-lookup"><span data-stu-id="001f8-143">Requirements</span></span>  
 <span data-ttu-id="001f8-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="001f8-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="001f8-145">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="001f8-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="001f8-146">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="001f8-146">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="001f8-147">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="001f8-147">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="001f8-148">См. также</span><span class="sxs-lookup"><span data-stu-id="001f8-148">See also</span></span>

- [<span data-ttu-id="001f8-149">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="001f8-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="001f8-150">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="001f8-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="001f8-151">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="001f8-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="001f8-152">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="001f8-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="001f8-153">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="001f8-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="001f8-154">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="001f8-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
