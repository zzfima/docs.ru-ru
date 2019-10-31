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
ms.openlocfilehash: a599e754202309a2b61d1761150f3f570fd0dc76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120412"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="ad772-102">Метод ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="ad772-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="ad772-103">Инициализирует среду CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="ad772-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad772-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad772-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ad772-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ad772-105">Return Value</span></span>  
  
|<span data-ttu-id="ad772-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad772-106">HRESULT</span></span>|<span data-ttu-id="ad772-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ad772-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad772-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad772-108">S_OK</span></span>|<span data-ttu-id="ad772-109">`Start` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ad772-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="ad772-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad772-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad772-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ad772-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad772-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad772-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad772-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ad772-113">The call timed out.</span></span>|  
|<span data-ttu-id="ad772-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad772-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad772-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ad772-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad772-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad772-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad772-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ad772-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad772-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad772-118">E_FAIL</span></span>|<span data-ttu-id="ad772-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ad772-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad772-120">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ad772-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad772-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ad772-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad772-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="ad772-122">Remarks</span></span>  
 <span data-ttu-id="ad772-123">Во многих случаях нет необходимости вызывать `Start`, так как среда выполнения инициализирует себя автоматически при первом запросе на выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ad772-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="ad772-124">Однако можно использовать `Start`, чтобы точно указать, когда должна быть инициализирована среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad772-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad772-125">Требования</span><span class="sxs-lookup"><span data-stu-id="ad772-125">Requirements</span></span>  
 <span data-ttu-id="ad772-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad772-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad772-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad772-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad772-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad772-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad772-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad772-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad772-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ad772-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="ad772-131">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ad772-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
