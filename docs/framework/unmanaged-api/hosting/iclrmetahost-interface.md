---
title: Интерфейс ICLRMetaHost
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b52b12df9953dbafaeebfe223313288de0e559b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584052"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="7e286-102">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="7e286-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="7e286-103">Предоставляет методы, которые возвращают определенную версию общеязыковой среды выполнения (CLR) в зависимости от номера версии, перечислены все установленные среды CLR, все среды выполнения, которые загружены в указанного процесса, версию среды CLR, используемый для компиляции сборки, выхода из процесса с помощью чистая среда завершение работы и устаревшие API привязки запроса.</span><span class="sxs-lookup"><span data-stu-id="7e286-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e286-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7e286-104">Methods</span></span>  
  
|<span data-ttu-id="7e286-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7e286-105">Method</span></span>|<span data-ttu-id="7e286-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7e286-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e286-107">Метод EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="7e286-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="7e286-108">Возвращает перечисление, содержащее допустимый [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой версии среды CLR, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e286-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="7e286-109">Метод EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="7e286-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="7e286-110">Возвращает перечисление, содержащее допустимый [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой среды CLR, который загружается в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="7e286-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="7e286-111">Этот метод заменяет [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="7e286-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="7e286-112">Метод ExitProcess</span><span class="sxs-lookup"><span data-stu-id="7e286-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="7e286-113">Пытается корректно завершить работу всех загруженных сред выполнения и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="7e286-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="7e286-114">Заменяет [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="7e286-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="7e286-115">Метод GetRuntime</span><span class="sxs-lookup"><span data-stu-id="7e286-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="7e286-116">Получает [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, который соответствует определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7e286-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="7e286-117">Этот метод заменяет [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функция, используемая с [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) флаг.</span><span class="sxs-lookup"><span data-stu-id="7e286-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="7e286-118">Метод GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="7e286-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="7e286-119">Получает сборки .NET Framework компиляции оригинального (хранится в метаданных), по его пути файла.</span><span class="sxs-lookup"><span data-stu-id="7e286-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="7e286-120">Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="7e286-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="7e286-121">Метод QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="7e286-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="7e286-122">Возвращает интерфейс, представляющий среду выполнения, к которому устаревшей политике активации привязки, например с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<startup > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) запись файла конфигурации, напрямую используя Устаревшие интерфейсы API активации или вызывая [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7e286-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="7e286-123">Метод RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="7e286-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="7e286-124">Гарантирует указанный указатель на функцию обратного вызова при первой загрузке версия среды CLR, но еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="7e286-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="7e286-125">Этот метод заменяет [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="7e286-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e286-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e286-126">Remarks</span></span>  
 <span data-ttu-id="7e286-127">Единственный способ получить экземпляр этого интерфейса — путем вызова [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) функцию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7e286-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7e286-128">Требования</span><span class="sxs-lookup"><span data-stu-id="7e286-128">Requirements</span></span>  
 <span data-ttu-id="7e286-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e286-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e286-130">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7e286-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e286-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e286-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e286-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e286-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e286-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7e286-133">See also</span></span>
- [<span data-ttu-id="7e286-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="7e286-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7e286-135">Размещение</span><span class="sxs-lookup"><span data-stu-id="7e286-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
