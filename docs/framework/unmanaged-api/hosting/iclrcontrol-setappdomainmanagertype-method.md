---
title: Метод ICLRControl::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: be29a4f83901b8e8fc338c2daa8f5703523402b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126588"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="1d7e2-102">Метод ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="1d7e2-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="1d7e2-103">Задает тип, производный от <xref:System.AppDomainManager> в качестве типа для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d7e2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d7e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d7e2-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="1d7e2-106">окне Имя сборки, в которой реализован запрошенный тип, производный от <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="1d7e2-107">окне Имя типа, реализованного в параметре `pwzAppDomainManagerAssembly`, который реализует возможности <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d7e2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d7e2-108">Return Value</span></span>  
  
|<span data-ttu-id="1d7e2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d7e2-109">HRESULT</span></span>|<span data-ttu-id="1d7e2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1d7e2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d7e2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d7e2-111">S_OK</span></span>|<span data-ttu-id="1d7e2-112">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="1d7e2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d7e2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d7e2-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d7e2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d7e2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d7e2-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-116">The call timed out.</span></span>|  
|<span data-ttu-id="1d7e2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d7e2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d7e2-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d7e2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d7e2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d7e2-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d7e2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d7e2-121">E_FAIL</span></span>|<span data-ttu-id="1d7e2-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d7e2-123">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d7e2-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d7e2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d7e2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="1d7e2-125">Requirements</span></span>  
 <span data-ttu-id="1d7e2-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7e2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7e2-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d7e2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d7e2-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d7e2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d7e2-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7e2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7e2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1d7e2-130">See also</span></span>

- [<span data-ttu-id="1d7e2-131">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1d7e2-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1d7e2-132">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="1d7e2-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
