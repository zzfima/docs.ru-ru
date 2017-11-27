---
title: "Метод ICLRControl::SetAppDomainManagerType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6632417cb0cfe17d7bde16ecf47ae1c001f43f2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="81204-102">Метод ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="81204-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="81204-103">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="81204-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81204-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81204-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81204-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81204-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="81204-106">[in] Имя сборки, в которой запрошенного типа производным от <xref:System.AppDomainManager> реализуется.</span><span class="sxs-lookup"><span data-stu-id="81204-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="81204-107">[in] Имя типа, реализованные в `pwzAppDomainManagerAssembly` параметр, который реализует возможности <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="81204-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81204-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81204-108">Return Value</span></span>  
  
|<span data-ttu-id="81204-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81204-109">HRESULT</span></span>|<span data-ttu-id="81204-110">Описание</span><span class="sxs-lookup"><span data-stu-id="81204-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81204-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="81204-111">S_OK</span></span>|<span data-ttu-id="81204-112">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="81204-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="81204-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81204-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81204-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="81204-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81204-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81204-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81204-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="81204-116">The call timed out.</span></span>|  
|<span data-ttu-id="81204-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81204-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81204-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="81204-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81204-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81204-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81204-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="81204-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81204-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81204-121">E_FAIL</span></span>|<span data-ttu-id="81204-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="81204-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81204-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="81204-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81204-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81204-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81204-125">Требования</span><span class="sxs-lookup"><span data-stu-id="81204-125">Requirements</span></span>  
 <span data-ttu-id="81204-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81204-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81204-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81204-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81204-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81204-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81204-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81204-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81204-130">См. также</span><span class="sxs-lookup"><span data-stu-id="81204-130">See Also</span></span>  
 [<span data-ttu-id="81204-131">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="81204-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="81204-132">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="81204-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
