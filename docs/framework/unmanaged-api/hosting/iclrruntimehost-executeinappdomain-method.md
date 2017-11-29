---
title: "Метода ICLRRuntimeHost::ExecuteInAppDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da6e9b52c0ea6f2935aad70779e159db91a4f501
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="4d5f8-102">Метода ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="4d5f8-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="4d5f8-103">Указывает <xref:System.AppDomain> в которой выполняется указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d5f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d5f8-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d5f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d5f8-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="4d5f8-106">[in] Числовой идентификатор объекта <xref:System.AppDomain> в котором для выполнения указанного метода.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="4d5f8-107">[in] Указатель на функцию, выполняемую в течение указанного <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="4d5f8-108">[in] Указатель на непрозрачные памяти, выделенный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="4d5f8-109">Этот параметр передается с общеязыковой среды выполнения (CLR) на обратный вызов домена.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="4d5f8-110">Не является управляемой средой выполнения динамической памяти; вызывающий объект управляет выделением и временем существования этой памяти.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d5f8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d5f8-111">Return Value</span></span>  
  
|<span data-ttu-id="4d5f8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d5f8-112">HRESULT</span></span>|<span data-ttu-id="4d5f8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4d5f8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d5f8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d5f8-114">S_OK</span></span>|<span data-ttu-id="4d5f8-115">`ExecuteInAppDomain`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="4d5f8-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d5f8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d5f8-117">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d5f8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d5f8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d5f8-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-119">The call timed out.</span></span>|  
|<span data-ttu-id="4d5f8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d5f8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d5f8-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d5f8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d5f8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d5f8-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d5f8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d5f8-124">E_FAIL</span></span>|<span data-ttu-id="4d5f8-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d5f8-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d5f8-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d5f8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d5f8-128">Remarks</span></span>  
 <span data-ttu-id="4d5f8-129">`ExecuteInAppDomain`предоставляет узлу возможность контроль которую управляемых <xref:System.AppDomain> указанного управляемого метода следует выполнять в.</span><span class="sxs-lookup"><span data-stu-id="4d5f8-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="4d5f8-130">Можно получить значение идентификатора домена приложения, который соответствует значению <xref:System.AppDomain.Id%2A> свойство путем вызова [GetCurrentAppDomainId-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="4d5f8-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d5f8-131">Требования</span><span class="sxs-lookup"><span data-stu-id="4d5f8-131">Requirements</span></span>  
 <span data-ttu-id="4d5f8-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d5f8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d5f8-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d5f8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d5f8-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d5f8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d5f8-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d5f8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5f8-136">См. также</span><span class="sxs-lookup"><span data-stu-id="4d5f8-136">See Also</span></span>  
 [<span data-ttu-id="4d5f8-137">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4d5f8-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
