---
title: "Метод ICLRRuntimeHost::Start"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26e1289aa22cda2ab744f1a2715259abbcafc59b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="e5f8d-102">Метод ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="e5f8d-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="e5f8d-103">Инициализирует общеязыковой среды выполнения (CLR) в процесс.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5f8d-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e5f8d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5f8d-105">Return Value</span></span>  
  
|<span data-ttu-id="e5f8d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5f8d-106">HRESULT</span></span>|<span data-ttu-id="e5f8d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e5f8d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5f8d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5f8d-108">S_OK</span></span>|<span data-ttu-id="e5f8d-109">`Start`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="e5f8d-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5f8d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5f8d-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5f8d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5f8d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5f8d-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-113">The call timed out.</span></span>|  
|<span data-ttu-id="e5f8d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5f8d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5f8d-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5f8d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5f8d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5f8d-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5f8d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5f8d-118">E_FAIL</span></span>|<span data-ttu-id="e5f8d-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5f8d-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5f8d-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5f8d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5f8d-122">Remarks</span></span>  
 <span data-ttu-id="e5f8d-123">Во многих случаях это не нужно вызывать `Start`, так как среда выполнения будет инициализироваться автоматически при первом запросе на выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="e5f8d-124">Однако, можно использовать `Start` для указания, только когда среда выполнения необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="e5f8d-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f8d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="e5f8d-125">Requirements</span></span>  
 <span data-ttu-id="e5f8d-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f8d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f8d-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5f8d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5f8d-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5f8d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5f8d-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f8d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f8d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e5f8d-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="e5f8d-131">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e5f8d-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
