---
title: Функция CorBindToRuntimeHost
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176491"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="b56e0-102">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b56e0-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="b56e0-103">Позволяет хостам загружать определенную версию общего времени выполнения языка (CLR) в процесс.</span><span class="sxs-lookup"><span data-stu-id="b56e0-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="b56e0-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="b56e0-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b56e0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b56e0-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b56e0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b56e0-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="b56e0-107">(в) Строка, описывающая версию CLR, которую вы хотите загрузить.</span><span class="sxs-lookup"><span data-stu-id="b56e0-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="b56e0-108">Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="b56e0-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="b56e0-109">Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").</span><span class="sxs-lookup"><span data-stu-id="b56e0-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="b56e0-110">Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR.</span><span class="sxs-lookup"><span data-stu-id="b56e0-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="b56e0-111">По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="b56e0-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="b56e0-112">Хост может заставить shim пропустить оценку `pwszVersion` политики и загрузить точную версию, указанную в, передавая значение STARTUP_LOADER_SAFEMODE для `startupFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="b56e0-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="b56e0-113">`null,` Если `pwszVersion` метод не загружает ни одной версии CLR.</span><span class="sxs-lookup"><span data-stu-id="b56e0-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="b56e0-114">Вместо этого он возвращает CLR_E_SHIM_RUNTIMELOAD, что указывает на то, что он не смог загрузить время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b56e0-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="b56e0-115">(в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR.</span><span class="sxs-lookup"><span data-stu-id="b56e0-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="b56e0-116">Допустимые значения: `svr` и `wks`.</span><span class="sxs-lookup"><span data-stu-id="b56e0-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="b56e0-117">Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.</span><span class="sxs-lookup"><span data-stu-id="b56e0-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="b56e0-118">Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается.</span><span class="sxs-lookup"><span data-stu-id="b56e0-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="b56e0-119">При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr`</span><span class="sxs-lookup"><span data-stu-id="b56e0-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="b56e0-120">Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `startupFlags` указан (см. описание параметра), сборка сервера загружается.</span><span class="sxs-lookup"><span data-stu-id="b56e0-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b56e0-121">Параллельный сбор мусора не поддерживается в приложениях под управлением эмулятора WOW64 x86 на 64-битных системах, реализуемых в архитектуре Intel Itanium (ранее именуемой IA-64).</span><span class="sxs-lookup"><span data-stu-id="b56e0-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="b56e0-122">Для получения дополнительной информации об использовании WOW64 на 64-битных системах Windows [см.](/windows/desktop/WinProg64/running-32-bit-applications)</span><span class="sxs-lookup"><span data-stu-id="b56e0-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="b56e0-123">(в) Название файла конфигурации хоста, который определяет версию CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="b56e0-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="b56e0-124">Если имя файла не включает полностью квалифицированный путь, предполагается, что файл находится в том же каталоге, что и исполняемый, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="b56e0-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="b56e0-125">(в) Зарезервировано для будущей расширяемости.</span><span class="sxs-lookup"><span data-stu-id="b56e0-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="b56e0-126">(в) Набор флагов, который контролирует параллельный сбор мусора, нейтральный код домена и поведение `pwszVersion` параметра.</span><span class="sxs-lookup"><span data-stu-id="b56e0-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="b56e0-127">По умолчанию один домен, если флаг не установлен.</span><span class="sxs-lookup"><span data-stu-id="b56e0-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="b56e0-128">Список поддерживаемых значений можно узнать [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="b56e0-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="b56e0-129">(в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)</span><span class="sxs-lookup"><span data-stu-id="b56e0-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="b56e0-130">Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="b56e0-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="b56e0-131">(в) Интерфейс, `IID` который вы запрашиваете.</span><span class="sxs-lookup"><span data-stu-id="b56e0-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="b56e0-132">Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="b56e0-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b56e0-133">(ваут) Указатель интерфейса к версии загруженного времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="b56e0-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b56e0-134">Требования</span><span class="sxs-lookup"><span data-stu-id="b56e0-134">Requirements</span></span>  
 <span data-ttu-id="b56e0-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b56e0-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b56e0-136">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b56e0-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b56e0-137">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b56e0-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b56e0-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b56e0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56e0-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b56e0-139">See also</span></span>

- [<span data-ttu-id="b56e0-140">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="b56e0-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="b56e0-141">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="b56e0-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="b56e0-142">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="b56e0-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="b56e0-143">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="b56e0-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="b56e0-144">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b56e0-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="b56e0-145">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b56e0-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
