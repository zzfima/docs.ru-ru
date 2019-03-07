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
ms.openlocfilehash: 06c3b060aaeb73b2d834c053cf47f0384ca4a38f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488474"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="36556-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="36556-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="36556-103">Получает указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="36556-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36556-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36556-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36556-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36556-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="36556-106">[out] Указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , позволяет узлам настроить дополнительные аспекты класса среды CLR.</span><span class="sxs-lookup"><span data-stu-id="36556-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36556-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="36556-107">Return Value</span></span>  
  
|<span data-ttu-id="36556-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36556-108">HRESULT</span></span>|<span data-ttu-id="36556-109">Описание</span><span class="sxs-lookup"><span data-stu-id="36556-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36556-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36556-110">S_OK</span></span>|<span data-ttu-id="36556-111">`GetCLRControl` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="36556-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="36556-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36556-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36556-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="36556-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36556-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36556-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36556-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="36556-115">The call timed out.</span></span>|  
|<span data-ttu-id="36556-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36556-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36556-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="36556-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36556-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36556-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36556-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="36556-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36556-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36556-120">E_FAIL</span></span>|<span data-ttu-id="36556-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="36556-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36556-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="36556-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36556-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="36556-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36556-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="36556-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="36556-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="36556-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36556-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="36556-126">Remarks</span></span>  
 <span data-ttu-id="36556-127">`ICLRControl` предоставляет [метод GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод, который позволяет ведущему приложению получить указатель интерфейса на один из типов manager.</span><span class="sxs-lookup"><span data-stu-id="36556-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36556-128">Требования</span><span class="sxs-lookup"><span data-stu-id="36556-128">Requirements</span></span>  
 <span data-ttu-id="36556-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36556-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36556-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36556-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36556-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36556-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36556-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36556-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36556-133">См. также</span><span class="sxs-lookup"><span data-stu-id="36556-133">See also</span></span>
- [<span data-ttu-id="36556-134">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="36556-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="36556-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="36556-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
