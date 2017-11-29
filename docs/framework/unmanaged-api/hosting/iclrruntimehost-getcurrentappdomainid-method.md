---
title: "Метод ICLRRuntimeHost::GetCurrentAppDomainId"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCurrentAppDomainId
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001a467536c899c3849b5689e65bdaf404beab75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="4cdd2-102">Метод ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="4cdd2-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="4cdd2-103">Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cdd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cdd2-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cdd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4cdd2-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="4cdd2-106">[out] Числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cdd2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4cdd2-107">Return Value</span></span>  
  
|<span data-ttu-id="4cdd2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cdd2-108">HRESULT</span></span>|<span data-ttu-id="4cdd2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4cdd2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cdd2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cdd2-110">S_OK</span></span>|<span data-ttu-id="4cdd2-111">`GetCurrentAppDomainId`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="4cdd2-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cdd2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cdd2-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cdd2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cdd2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cdd2-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-115">The call timed out.</span></span>|  
|<span data-ttu-id="4cdd2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cdd2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cdd2-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cdd2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cdd2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cdd2-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cdd2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cdd2-120">E_FAIL</span></span>|<span data-ttu-id="4cdd2-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cdd2-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cdd2-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cdd2-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="4cdd2-124">Remarks</span></span>  
 <span data-ttu-id="4cdd2-125">`pdwAppDomainId` Установлено значение <xref:System.AppDomain.Id%2A> свойство <xref:System.AppDomain> , в которой выполняется текущий поток.</span><span class="sxs-lookup"><span data-stu-id="4cdd2-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cdd2-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4cdd2-126">Requirements</span></span>  
 <span data-ttu-id="4cdd2-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cdd2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cdd2-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cdd2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cdd2-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cdd2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cdd2-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cdd2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cdd2-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4cdd2-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="4cdd2-132">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4cdd2-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
