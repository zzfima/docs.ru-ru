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
ms.openlocfilehash: 97a0e6cbbd8972f58f9eedcfeb8aff1f93694064
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765668"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="2ae70-102">Метод ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="2ae70-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="2ae70-103">Прекращает выполнение кода, общеязыковая среда выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="2ae70-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ae70-104">Этот метод не освобождать ресурсы на узле выгрузки доменов приложений и уничтожение потоков.</span><span class="sxs-lookup"><span data-stu-id="2ae70-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="2ae70-105">Необходимо завершить процесс, чтобы освободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2ae70-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae70-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ae70-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2ae70-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ae70-107">Return Value</span></span>  
  
|<span data-ttu-id="2ae70-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ae70-108">HRESULT</span></span>|<span data-ttu-id="2ae70-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2ae70-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ae70-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ae70-110">S_OK</span></span>|<span data-ttu-id="2ae70-111">`Stop` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2ae70-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="2ae70-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ae70-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ae70-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2ae70-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ae70-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ae70-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ae70-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2ae70-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ae70-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ae70-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ae70-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2ae70-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ae70-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ae70-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ae70-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2ae70-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ae70-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ae70-120">E_FAIL</span></span>|<span data-ttu-id="2ae70-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2ae70-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ae70-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2ae70-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ae70-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ae70-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ae70-124">Требования</span><span class="sxs-lookup"><span data-stu-id="2ae70-124">Requirements</span></span>  
 <span data-ttu-id="2ae70-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ae70-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae70-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ae70-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ae70-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ae70-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ae70-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae70-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae70-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2ae70-129">See also</span></span>

- [<span data-ttu-id="2ae70-130">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2ae70-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
