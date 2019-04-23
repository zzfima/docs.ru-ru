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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86348c35a023e22d10c4ad2e08f5cb1104b895a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165505"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="973d6-102">Метода ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="973d6-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="973d6-103">Указывает <xref:System.AppDomain> в которой выполняется указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="973d6-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="973d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="973d6-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="973d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="973d6-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="973d6-106">[in] Числовой идентификатор <xref:System.AppDomain> для выполнения указанного метода.</span><span class="sxs-lookup"><span data-stu-id="973d6-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="973d6-107">[in] Указатель на функцию, выполняемую в течение указанного <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="973d6-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="973d6-108">[in] Указатель на непрозрачные памяти, выделенный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="973d6-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="973d6-109">Этот параметр передается по общеязыковой среды выполнения (CLR) методу обратного вызова домена.</span><span class="sxs-lookup"><span data-stu-id="973d6-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="973d6-110">Не является управляемой средой выполнения динамической памяти; вызывающий объект управляет выделением и временем существования этой памяти.</span><span class="sxs-lookup"><span data-stu-id="973d6-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="973d6-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="973d6-111">Return Value</span></span>  
  
|<span data-ttu-id="973d6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="973d6-112">HRESULT</span></span>|<span data-ttu-id="973d6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="973d6-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="973d6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="973d6-114">S_OK</span></span>|<span data-ttu-id="973d6-115">`ExecuteInAppDomain` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="973d6-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="973d6-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="973d6-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="973d6-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="973d6-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="973d6-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="973d6-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="973d6-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="973d6-119">The call timed out.</span></span>|  
|<span data-ttu-id="973d6-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="973d6-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="973d6-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="973d6-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="973d6-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="973d6-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="973d6-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="973d6-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="973d6-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="973d6-124">E_FAIL</span></span>|<span data-ttu-id="973d6-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="973d6-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="973d6-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="973d6-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="973d6-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="973d6-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="973d6-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="973d6-128">Remarks</span></span>  
 <span data-ttu-id="973d6-129">`ExecuteInAppDomain` позволяет узлу для контроля над котором управляемых <xref:System.AppDomain> указанного управляемого метода должен быть выполнен в.</span><span class="sxs-lookup"><span data-stu-id="973d6-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="973d6-130">Можно получить значение идентификатора домен приложения, который соответствует значению <xref:System.AppDomain.Id%2A> свойства, путем вызова [метод GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="973d6-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="973d6-131">Требования</span><span class="sxs-lookup"><span data-stu-id="973d6-131">Requirements</span></span>  
 <span data-ttu-id="973d6-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="973d6-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="973d6-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="973d6-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="973d6-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="973d6-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="973d6-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="973d6-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="973d6-136">См. также</span><span class="sxs-lookup"><span data-stu-id="973d6-136">See also</span></span>

- [<span data-ttu-id="973d6-137">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="973d6-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
