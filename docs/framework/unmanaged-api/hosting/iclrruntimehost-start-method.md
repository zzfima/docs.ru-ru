---
title: Метод ICLRRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c969cbda8fdaf8fa418c2246f3d0937e622250
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765742"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="674f7-102">Метод ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="674f7-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="674f7-103">Инициализирует общеязыковой среды выполнения (CLR) в процесс.</span><span class="sxs-lookup"><span data-stu-id="674f7-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="674f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="674f7-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="674f7-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="674f7-105">Return Value</span></span>  
  
|<span data-ttu-id="674f7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="674f7-106">HRESULT</span></span>|<span data-ttu-id="674f7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="674f7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="674f7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="674f7-108">S_OK</span></span>|<span data-ttu-id="674f7-109">`Start` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="674f7-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="674f7-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="674f7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="674f7-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="674f7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="674f7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="674f7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="674f7-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="674f7-113">The call timed out.</span></span>|  
|<span data-ttu-id="674f7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="674f7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="674f7-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="674f7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="674f7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="674f7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="674f7-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="674f7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="674f7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="674f7-118">E_FAIL</span></span>|<span data-ttu-id="674f7-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="674f7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="674f7-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="674f7-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="674f7-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="674f7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="674f7-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="674f7-122">Remarks</span></span>  
 <span data-ttu-id="674f7-123">Во многих случаях это не нужно вызывать `Start`, так как среда выполнения будет инициализироваться автоматически при первом запросе для запуска управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="674f7-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="674f7-124">Тем не менее, можно использовать `Start` для указания, только когда среда выполнения должна быть инициализирована.</span><span class="sxs-lookup"><span data-stu-id="674f7-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="674f7-125">Требования</span><span class="sxs-lookup"><span data-stu-id="674f7-125">Requirements</span></span>  
 <span data-ttu-id="674f7-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="674f7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="674f7-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="674f7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="674f7-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="674f7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="674f7-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="674f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="674f7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="674f7-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="674f7-131">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="674f7-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
