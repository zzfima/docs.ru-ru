---
title: Метод ICLRRuntimeHost::GetCLRControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b697e2cf7688767ac58c6bd2a3f18d781ab439b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768754"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="2fc79-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="2fc79-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="2fc79-103">Получает указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="2fc79-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fc79-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fc79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fc79-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="2fc79-106">[out] Указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , позволяет узлам настроить дополнительные аспекты класса среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2fc79-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fc79-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2fc79-107">Return Value</span></span>  
  
|<span data-ttu-id="2fc79-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fc79-108">HRESULT</span></span>|<span data-ttu-id="2fc79-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2fc79-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fc79-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fc79-110">S_OK</span></span>|<span data-ttu-id="2fc79-111">`GetCLRControl` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2fc79-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="2fc79-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fc79-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fc79-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2fc79-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2fc79-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fc79-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fc79-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2fc79-115">The call timed out.</span></span>|  
|<span data-ttu-id="2fc79-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fc79-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fc79-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2fc79-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fc79-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fc79-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fc79-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2fc79-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fc79-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fc79-120">E_FAIL</span></span>|<span data-ttu-id="2fc79-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2fc79-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fc79-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2fc79-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fc79-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2fc79-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2fc79-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2fc79-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="2fc79-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="2fc79-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fc79-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fc79-126">Remarks</span></span>  
 <span data-ttu-id="2fc79-127">`ICLRControl` предоставляет [метод GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод, который позволяет ведущему приложению получить указатель интерфейса на один из типов manager.</span><span class="sxs-lookup"><span data-stu-id="2fc79-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fc79-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2fc79-128">Requirements</span></span>  
 <span data-ttu-id="2fc79-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fc79-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc79-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fc79-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fc79-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fc79-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fc79-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc79-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc79-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc79-133">See also</span></span>

- [<span data-ttu-id="2fc79-134">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2fc79-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2fc79-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2fc79-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
