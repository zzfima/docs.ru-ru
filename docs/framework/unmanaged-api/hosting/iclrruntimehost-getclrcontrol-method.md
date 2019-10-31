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
ms.openlocfilehash: 478e07f18d40043de4e800c36647ac4a32499635
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120434"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="2da48-102">Метод ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="2da48-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="2da48-103">Возвращает указатель интерфейса типа [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2da48-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2da48-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2da48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2da48-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="2da48-106">заполняет Указатель интерфейса типа [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , который позволяет узлам настраивать дополнительные аспекты среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2da48-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2da48-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2da48-107">Return Value</span></span>  
  
|<span data-ttu-id="2da48-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2da48-108">HRESULT</span></span>|<span data-ttu-id="2da48-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2da48-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2da48-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2da48-110">S_OK</span></span>|<span data-ttu-id="2da48-111">`GetCLRControl` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2da48-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="2da48-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2da48-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2da48-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2da48-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2da48-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2da48-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2da48-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2da48-115">The call timed out.</span></span>|  
|<span data-ttu-id="2da48-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2da48-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2da48-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2da48-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2da48-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2da48-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2da48-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2da48-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2da48-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2da48-120">E_FAIL</span></span>|<span data-ttu-id="2da48-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2da48-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2da48-122">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2da48-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2da48-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2da48-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2da48-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2da48-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="2da48-125">Среда CLR уже запущена.</span><span class="sxs-lookup"><span data-stu-id="2da48-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2da48-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="2da48-126">Remarks</span></span>  
 <span data-ttu-id="2da48-127">`ICLRControl` предоставляет метод [метода GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) , который позволяет узлу получить указатель интерфейса на один из типов диспетчера.</span><span class="sxs-lookup"><span data-stu-id="2da48-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2da48-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2da48-128">Requirements</span></span>  
 <span data-ttu-id="2da48-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2da48-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2da48-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2da48-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2da48-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2da48-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2da48-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2da48-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da48-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2da48-133">See also</span></span>

- [<span data-ttu-id="2da48-134">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2da48-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2da48-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2da48-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
