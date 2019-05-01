---
title: Перечисление STARTUP_FLAGS
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05ff93f9dc7e875c9f84dd6d8d1f4be9b4f12653
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043515"
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="1174f-102">Перечисление STARTUP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1174f-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="1174f-103">Содержит значения, указывающие поведение при запуске общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1174f-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="1174f-104">По умолчанию, сбора мусора связана с непараллельной, а только библиотеки базовых классов загружаются в область нейтральных к домену.</span><span class="sxs-lookup"><span data-stu-id="1174f-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1174f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1174f-105">Syntax</span></span>  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1174f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="1174f-106">Members</span></span>  
  
|<span data-ttu-id="1174f-107">Член</span><span class="sxs-lookup"><span data-stu-id="1174f-107">Member</span></span>|<span data-ttu-id="1174f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1174f-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="1174f-109">Указывает, что следует использовать параллельную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="1174f-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="1174f-110">Если вызывающий объект запрашивает сервер сборки и параллельная сборка мусора на однопроцессорном компьютере, вместо этого выполняются построение рабочей станции и непараллельной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1174f-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="1174f-111">**Примечание.**  Параллельная сборка мусора не поддерживается в приложениях, работающих под управлением WOW64 x86 эмулятора на 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64).</span><span class="sxs-lookup"><span data-stu-id="1174f-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="1174f-112">Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows, см. в разделе [под управлением 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="1174f-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="1174f-113">Указывает, что этой оптимизации загрузчика.</span><span class="sxs-lookup"><span data-stu-id="1174f-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="1174f-114">Указывает, что сборки не загружены как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="1174f-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="1174f-115">Указывает, что все сборки загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="1174f-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="1174f-116">Указывает, что все сборки со строгими именами загружаются как нейтральные к домену.</span><span class="sxs-lookup"><span data-stu-id="1174f-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="1174f-117">Указывает, что политика версии среды CLR не будет применяться к переданной версии.</span><span class="sxs-lookup"><span data-stu-id="1174f-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="1174f-118">Указанная версия среды CLR будут загружены.</span><span class="sxs-lookup"><span data-stu-id="1174f-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="1174f-119">Оболочки совместимости не оценивает политику, чтобы определить последнюю совместимую версию.</span><span class="sxs-lookup"><span data-stu-id="1174f-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="1174f-120">Указывает предпочтительная среда выполнения будет задать, но фактически не запущена.</span><span class="sxs-lookup"><span data-stu-id="1174f-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="1174f-121">Указывает, что сборка мусора сервера будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="1174f-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="1174f-122">Указывает, что сборка мусора будет хранить виртуальный адрес, используемый.</span><span class="sxs-lookup"><span data-stu-id="1174f-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="1174f-123">Указывает, что смешивание интерфейс размещения будет запрещено.</span><span class="sxs-lookup"><span data-stu-id="1174f-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="1174f-124">Указывает, что олицетворение следует не проходит через асинхронные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1174f-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="1174f-125">Указывает, что всего стека потоков не будут зафиксированы при запуске потока.</span><span class="sxs-lookup"><span data-stu-id="1174f-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="1174f-126">Указывает, что управляемые олицетворения и олицетворения, полученные посредством invoke будет проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="1174f-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="1174f-127">По умолчанию только управляемые олицетворения будет проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="1174f-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="1174f-128">Указывает, что сборка мусора будет использовать менее выделяемого объема, когда недостаточно системной памяти.</span><span class="sxs-lookup"><span data-stu-id="1174f-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="1174f-129">См. в разделе `gcTrimCommitOnLowMemory` в [оптимизации для общих веб-размещения](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="1174f-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="1174f-130">Включение трассировки событий для Windows (ETW) для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1174f-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="1174f-131">Начиная с Windows Vista, трассировка событий всегда включена, поэтому этот флаг не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="1174f-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="1174f-132">См. в разделе [контроль ведения журнала .NET Framework](../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="1174f-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="1174f-133">Указывает, что включено отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="1174f-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="1174f-134">См. в разделе <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> свойство и [ \<appDomainResourceMonitoring > элемент](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="1174f-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1174f-135">Требования</span><span class="sxs-lookup"><span data-stu-id="1174f-135">Requirements</span></span>  
 <span data-ttu-id="1174f-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1174f-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1174f-137">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1174f-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1174f-138">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1174f-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1174f-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1174f-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1174f-140">См. также</span><span class="sxs-lookup"><span data-stu-id="1174f-140">See also</span></span>

- [<span data-ttu-id="1174f-141">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="1174f-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
