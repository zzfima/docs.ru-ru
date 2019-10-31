---
title: Метода ICLRRuntimeHost::ExecuteInAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120492"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="52e8d-102">Метода ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="52e8d-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="52e8d-103">Указывает <xref:System.AppDomain>, в котором будет выполняться указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="52e8d-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52e8d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52e8d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52e8d-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="52e8d-106">окне Числовой идентификатор <xref:System.AppDomain>, в котором будет выполняться указанный метод.</span><span class="sxs-lookup"><span data-stu-id="52e8d-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="52e8d-107">окне Указатель на функцию, которую необходимо выполнить в указанном <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="52e8d-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="52e8d-108">окне Указатель на непрозрачную память, выделенную вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="52e8d-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="52e8d-109">Этот параметр передается средой CLR в обратный вызов домена.</span><span class="sxs-lookup"><span data-stu-id="52e8d-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="52e8d-110">Это не управляемая средой выполнения память кучи; как выделение, так и время существования этой памяти контролируются вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="52e8d-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52e8d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="52e8d-111">Return Value</span></span>  
  
|<span data-ttu-id="52e8d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52e8d-112">HRESULT</span></span>|<span data-ttu-id="52e8d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="52e8d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52e8d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="52e8d-114">S_OK</span></span>|<span data-ttu-id="52e8d-115">`ExecuteInAppDomain` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="52e8d-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="52e8d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52e8d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52e8d-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="52e8d-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52e8d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52e8d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52e8d-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="52e8d-119">The call timed out.</span></span>|  
|<span data-ttu-id="52e8d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52e8d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52e8d-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="52e8d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52e8d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52e8d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52e8d-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="52e8d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52e8d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52e8d-124">E_FAIL</span></span>|<span data-ttu-id="52e8d-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="52e8d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52e8d-126">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="52e8d-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52e8d-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52e8d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e8d-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="52e8d-128">Remarks</span></span>  
 <span data-ttu-id="52e8d-129">`ExecuteInAppDomain` позволяет узлу выполнять контроль над тем, какие управляемые <xref:System.AppDomain> указанный управляемый метод должен выполняться в.</span><span class="sxs-lookup"><span data-stu-id="52e8d-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="52e8d-130">Можно получить значение идентификатора домена приложения, которое соответствует значению свойства <xref:System.AppDomain.Id%2A>, вызвав [метод жеткуррентаппдомаинид](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="52e8d-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52e8d-131">Требования</span><span class="sxs-lookup"><span data-stu-id="52e8d-131">Requirements</span></span>  
 <span data-ttu-id="52e8d-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52e8d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e8d-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="52e8d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52e8d-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="52e8d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52e8d-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e8d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e8d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="52e8d-136">See also</span></span>

- [<span data-ttu-id="52e8d-137">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="52e8d-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
