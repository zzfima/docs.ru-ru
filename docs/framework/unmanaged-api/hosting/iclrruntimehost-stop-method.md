---
title: "Метод ICLRRuntimeHost::Stop"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3798c4fc451b78257373c0ac47a5e7e7c27dd048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="3666f-102">Метод ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="3666f-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3666f-103">Останавливает выполнение кода средой CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="3666f-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3666f-104">Этот метод не освобождать ресурсы на узле, выгрузки доменов приложений и не удаляет потоки.</span><span class="sxs-lookup"><span data-stu-id="3666f-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="3666f-105">Необходимо завершить процесс для высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3666f-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3666f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3666f-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3666f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3666f-107">Return Value</span></span>  
  
|<span data-ttu-id="3666f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3666f-108">HRESULT</span></span>|<span data-ttu-id="3666f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3666f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3666f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3666f-110">S_OK</span></span>|<span data-ttu-id="3666f-111">`Stop`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3666f-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="3666f-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3666f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3666f-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3666f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3666f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3666f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3666f-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3666f-115">The call timed out.</span></span>|  
|<span data-ttu-id="3666f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3666f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3666f-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3666f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3666f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3666f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3666f-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3666f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3666f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3666f-120">E_FAIL</span></span>|<span data-ttu-id="3666f-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3666f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3666f-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3666f-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3666f-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3666f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3666f-124">Требования</span><span class="sxs-lookup"><span data-stu-id="3666f-124">Requirements</span></span>  
 <span data-ttu-id="3666f-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3666f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3666f-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3666f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3666f-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3666f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3666f-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3666f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3666f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3666f-129">See Also</span></span>  
 [<span data-ttu-id="3666f-130">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3666f-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
