---
title: "Метод ICLRMetaHost::EnumerateLoadedRuntimes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.EnumerateLoadedRuntimes
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0724bf44eaf82b39262876ea4a44509b6c7d576
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="3cfa0-102">Метод ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="3cfa0-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="3cfa0-103">Возвращает перечисление, которое содержит допустимый [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой версии среды common language runtime (CLR), загружаемой в данный процесс.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="3cfa0-104">Этот метод заменяет [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfa0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cfa0-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cfa0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cfa0-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="3cfa0-107">[in] Дескриптор процесса проверки для загрузки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="3cfa0-108">[out] <!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown` Перечисление [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейсов, связанных с каждой среды CLR, загруженные процессом.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-108">[out] An <!--zz <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>--> `Microsoft.VisualStudio.OLE.Interop.IEnumUnknown` enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cfa0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3cfa0-109">Return Value</span></span>  
 <span data-ttu-id="3cfa0-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3cfa0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cfa0-111">HRESULT</span></span>|<span data-ttu-id="3cfa0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3cfa0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cfa0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cfa0-113">S_OK</span></span>|<span data-ttu-id="3cfa0-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="3cfa0-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3cfa0-115">E_POINTER</span></span>|<span data-ttu-id="3cfa0-116">Параметр `ppEnumerator` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3cfa0-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cfa0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cfa0-117">Remarks</span></span>  
 <span data-ttu-id="3cfa0-118">Этот метод является список всех загрузки среды выполнения, даже если они загруженных с нерекомендуемых функций, таких как [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa0-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfa0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3cfa0-119">Requirements</span></span>  
 <span data-ttu-id="3cfa0-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfa0-121">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3cfa0-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3cfa0-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cfa0-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cfa0-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cfa0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cfa0-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3cfa0-124">See Also</span></span>  
 [<span data-ttu-id="3cfa0-125">ICLRMetaHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3cfa0-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="3cfa0-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="3cfa0-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
