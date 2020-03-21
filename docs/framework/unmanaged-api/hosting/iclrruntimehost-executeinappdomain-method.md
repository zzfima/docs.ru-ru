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
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176426"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="2c939-102">Метода ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="2c939-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="2c939-103">Указать, в <xref:System.AppDomain> каком случае выполняется указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="2c939-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c939-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c939-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c939-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c939-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="2c939-106">(в) Числовый идентификатор, <xref:System.AppDomain> в котором выполняется указанный метод.</span><span class="sxs-lookup"><span data-stu-id="2c939-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="2c939-107">(в) Указатель на функцию для выполнения <xref:System.AppDomain>в указанном .</span><span class="sxs-lookup"><span data-stu-id="2c939-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="2c939-108">(в) Указатель на непрозрачную память, выделенную абонентом.</span><span class="sxs-lookup"><span data-stu-id="2c939-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="2c939-109">Этот параметр передается общим временем выполнения языка (CLR) на обратный вызов домена.</span><span class="sxs-lookup"><span data-stu-id="2c939-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="2c939-110">Это не время выполнения управляемой кучей памяти; как распределение, так и срок службы этой памяти контролируется абонентом.</span><span class="sxs-lookup"><span data-stu-id="2c939-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c939-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c939-111">Return Value</span></span>  
  
|<span data-ttu-id="2c939-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c939-112">HRESULT</span></span>|<span data-ttu-id="2c939-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2c939-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c939-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c939-114">S_OK</span></span>|<span data-ttu-id="2c939-115">`ExecuteInAppDomain`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="2c939-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="2c939-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c939-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c939-117">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2c939-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c939-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c939-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c939-119">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="2c939-119">The call timed out.</span></span>|  
|<span data-ttu-id="2c939-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c939-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c939-121">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="2c939-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c939-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c939-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c939-123">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="2c939-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c939-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c939-124">E_FAIL</span></span>|<span data-ttu-id="2c939-125">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="2c939-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c939-126">Если метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе.</span><span class="sxs-lookup"><span data-stu-id="2c939-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c939-127">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c939-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c939-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c939-128">Remarks</span></span>  
 <span data-ttu-id="2c939-129">`ExecuteInAppDomain`позволяет усусу осуществлять <xref:System.AppDomain> контроль над тем, в котором должен быть выполнен указанный управляемый метод.</span><span class="sxs-lookup"><span data-stu-id="2c939-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="2c939-130">Вы можете получить стоимость идентификатора домена приложения, который <xref:System.AppDomain.Id%2A> соответствует стоимости свойства, позвонив в [GetCurrentAppDomainId Method.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)</span><span class="sxs-lookup"><span data-stu-id="2c939-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c939-131">Требования</span><span class="sxs-lookup"><span data-stu-id="2c939-131">Requirements</span></span>  
 <span data-ttu-id="2c939-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c939-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c939-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c939-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c939-134">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c939-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c939-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c939-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c939-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c939-136">See also</span></span>

- [<span data-ttu-id="2c939-137">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2c939-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
