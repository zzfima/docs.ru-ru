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
ms.openlocfilehash: 83b029c24321946f777966daa7a486f9e8e7b7a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073152"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="cec80-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="cec80-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="cec80-103">Получает указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="cec80-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cec80-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cec80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cec80-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="cec80-106">[out] Указатель интерфейса типа [интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , позволяет узлам настроить дополнительные аспекты класса среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cec80-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cec80-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cec80-107">Return Value</span></span>  
  
|<span data-ttu-id="cec80-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cec80-108">HRESULT</span></span>|<span data-ttu-id="cec80-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cec80-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cec80-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cec80-110">S_OK</span></span>|`GetCLRControl` <span data-ttu-id="cec80-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cec80-111">returned successfully.</span></span>|  
|<span data-ttu-id="cec80-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cec80-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cec80-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cec80-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cec80-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cec80-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cec80-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cec80-115">The call timed out.</span></span>|  
|<span data-ttu-id="cec80-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cec80-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cec80-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cec80-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cec80-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cec80-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cec80-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cec80-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cec80-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cec80-120">E_FAIL</span></span>|<span data-ttu-id="cec80-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="cec80-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cec80-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cec80-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cec80-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cec80-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cec80-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="cec80-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="cec80-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="cec80-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cec80-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="cec80-126">Remarks</span></span>  
 `ICLRControl` <span data-ttu-id="cec80-127">предоставляет [метод GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод, который позволяет ведущему приложению получить указатель интерфейса на один из типов manager.</span><span class="sxs-lookup"><span data-stu-id="cec80-127">provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec80-128">Требования</span><span class="sxs-lookup"><span data-stu-id="cec80-128">Requirements</span></span>  
 <span data-ttu-id="cec80-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cec80-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cec80-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cec80-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cec80-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cec80-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cec80-132">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cec80-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cec80-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cec80-133">See also</span></span>

- [<span data-ttu-id="cec80-134">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cec80-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cec80-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cec80-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
