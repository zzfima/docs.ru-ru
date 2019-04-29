---
title: Метод ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971669"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="0d859-102">Метод ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="0d859-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="0d859-103">Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="0d859-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d859-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d859-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d859-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d859-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="0d859-106">[out] Числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="0d859-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d859-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d859-107">Return Value</span></span>  
  
|<span data-ttu-id="0d859-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d859-108">HRESULT</span></span>|<span data-ttu-id="0d859-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0d859-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d859-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d859-110">S_OK</span></span>|<span data-ttu-id="0d859-111">`GetCurrentAppDomainId` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0d859-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="0d859-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d859-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d859-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0d859-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d859-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d859-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d859-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0d859-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d859-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d859-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d859-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0d859-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d859-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d859-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d859-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0d859-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d859-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d859-120">E_FAIL</span></span>|<span data-ttu-id="0d859-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0d859-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d859-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0d859-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d859-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d859-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d859-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d859-124">Remarks</span></span>  
 <span data-ttu-id="0d859-125">`pdwAppDomainId` Параметру присвоить значение <xref:System.AppDomain.Id%2A> свойство <xref:System.AppDomain> в которой выполняется текущий поток.</span><span class="sxs-lookup"><span data-stu-id="0d859-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d859-126">Требования</span><span class="sxs-lookup"><span data-stu-id="0d859-126">Requirements</span></span>  
 <span data-ttu-id="0d859-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d859-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d859-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d859-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d859-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d859-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d859-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d859-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d859-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0d859-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="0d859-132">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0d859-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
