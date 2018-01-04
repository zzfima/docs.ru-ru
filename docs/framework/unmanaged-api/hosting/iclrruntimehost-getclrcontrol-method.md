---
title: "Метод ICLRRuntimeHost::GetCLRControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc8cc80e24e3dd03d3c179d91fe16b8391502bf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="8a3f6-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="8a3f6-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="8a3f6-103">Получает указатель интерфейса типа [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8a3f6-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a3f6-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a3f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a3f6-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="8a3f6-106">[out] Указатель на интерфейс типа [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , позволяет узлам настраивать дополнительные параметры среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3f6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a3f6-107">Return Value</span></span>  
  
|<span data-ttu-id="8a3f6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a3f6-108">HRESULT</span></span>|<span data-ttu-id="8a3f6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3f6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a3f6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a3f6-110">S_OK</span></span>|<span data-ttu-id="8a3f6-111">`GetCLRControl`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="8a3f6-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a3f6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a3f6-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a3f6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a3f6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a3f6-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-115">The call timed out.</span></span>|  
|<span data-ttu-id="8a3f6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a3f6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a3f6-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a3f6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a3f6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a3f6-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a3f6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a3f6-120">E_FAIL</span></span>|<span data-ttu-id="8a3f6-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a3f6-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a3f6-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8a3f6-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8a3f6-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8a3f6-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3f6-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a3f6-126">Remarks</span></span>  
 <span data-ttu-id="8a3f6-127">`ICLRControl`предоставляет [getclrmanager-метод](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод, который позволяет ведущему приложению получить указатель интерфейса на один из типов manager.</span><span class="sxs-lookup"><span data-stu-id="8a3f6-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3f6-128">Требования</span><span class="sxs-lookup"><span data-stu-id="8a3f6-128">Requirements</span></span>  
 <span data-ttu-id="8a3f6-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3f6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3f6-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a3f6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a3f6-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a3f6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a3f6-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3f6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3f6-133">См. также</span><span class="sxs-lookup"><span data-stu-id="8a3f6-133">See Also</span></span>  
 [<span data-ttu-id="8a3f6-134">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8a3f6-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8a3f6-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8a3f6-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
