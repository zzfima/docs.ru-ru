---
title: Метод ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db10b5c67a098cc34292a2680bd832f9cef2861b
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584108"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="4916b-102">Метод ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="4916b-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="4916b-103">Возвращает перечисление, которое содержит допустимый [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой версии CLR (CLR), загружается в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="4916b-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="4916b-104">Этот метод заменяет [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4916b-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4916b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4916b-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4916b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4916b-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="4916b-107">[in] Дескриптор процесса для проверки на наличие загруженных сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="4916b-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="4916b-108">[out] <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Перечисление [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейсов, связанных с каждой среды CLR, загруженные процессом.</span><span class="sxs-lookup"><span data-stu-id="4916b-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4916b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4916b-109">Return Value</span></span>  
 <span data-ttu-id="4916b-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="4916b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4916b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4916b-111">HRESULT</span></span>|<span data-ttu-id="4916b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4916b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4916b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4916b-113">S_OK</span></span>|<span data-ttu-id="4916b-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="4916b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="4916b-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4916b-115">E_POINTER</span></span>|<span data-ttu-id="4916b-116">Параметр `ppEnumerator` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="4916b-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4916b-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="4916b-117">Remarks</span></span>  
 <span data-ttu-id="4916b-118">Этот метод является список всех загрузки среды выполнения, даже если они загружены с устаревшие функции, такие как [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="4916b-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4916b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4916b-119">Requirements</span></span>  
 <span data-ttu-id="4916b-120">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4916b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4916b-121">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4916b-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4916b-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4916b-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4916b-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4916b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4916b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4916b-124">See Also</span></span>  
 [<span data-ttu-id="4916b-125">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="4916b-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="4916b-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="4916b-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
