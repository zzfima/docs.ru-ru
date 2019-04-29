---
title: Метод ICLRRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771837"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="e03ed-102">Метод ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="e03ed-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e03ed-103">Прекращает выполнение кода, общеязыковая среда выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="e03ed-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e03ed-104">Этот метод не освобождать ресурсы на узле выгрузки доменов приложений и уничтожение потоков.</span><span class="sxs-lookup"><span data-stu-id="e03ed-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="e03ed-105">Необходимо завершить процесс, чтобы освободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="e03ed-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03ed-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e03ed-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e03ed-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e03ed-107">Return Value</span></span>  
  
|<span data-ttu-id="e03ed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e03ed-108">HRESULT</span></span>|<span data-ttu-id="e03ed-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e03ed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e03ed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e03ed-110">S_OK</span></span>|<span data-ttu-id="e03ed-111">`Stop` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e03ed-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="e03ed-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e03ed-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e03ed-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e03ed-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e03ed-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e03ed-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e03ed-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e03ed-115">The call timed out.</span></span>|  
|<span data-ttu-id="e03ed-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e03ed-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e03ed-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e03ed-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e03ed-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e03ed-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e03ed-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e03ed-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e03ed-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e03ed-120">E_FAIL</span></span>|<span data-ttu-id="e03ed-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e03ed-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e03ed-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e03ed-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e03ed-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e03ed-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e03ed-124">Требования</span><span class="sxs-lookup"><span data-stu-id="e03ed-124">Requirements</span></span>  
 <span data-ttu-id="e03ed-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e03ed-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e03ed-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e03ed-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e03ed-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e03ed-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e03ed-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e03ed-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03ed-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e03ed-129">See also</span></span>

- [<span data-ttu-id="e03ed-130">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e03ed-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
