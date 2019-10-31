---
title: Метод IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134727"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="83877-102">Метод IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="83877-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="83877-103">Уведомляет узел о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="83877-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83877-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83877-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83877-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83877-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="83877-106">окне Числовой идентификатор выбранного <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="83877-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="83877-107">окне Указатель на объект <xref:System.AppDomainManager>, который реализуется узлом как `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="83877-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83877-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83877-108">Return Value</span></span>  
  
|<span data-ttu-id="83877-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83877-109">HRESULT</span></span>|<span data-ttu-id="83877-110">Описание</span><span class="sxs-lookup"><span data-stu-id="83877-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83877-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="83877-111">S_OK</span></span>|<span data-ttu-id="83877-112">`SetAppDomainManager` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="83877-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="83877-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83877-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83877-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="83877-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83877-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83877-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83877-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="83877-116">The call timed out.</span></span>|  
|<span data-ttu-id="83877-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83877-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83877-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="83877-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83877-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83877-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83877-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="83877-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83877-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83877-121">E_FAIL</span></span>|<span data-ttu-id="83877-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="83877-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83877-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="83877-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83877-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="83877-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83877-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="83877-125">Remarks</span></span>  
 <span data-ttu-id="83877-126"><xref:System.AppDomainManager> предоставляет узлу механизм для начальной загрузки в управляемый код и управления созданием и параметрами каждого <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="83877-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="83877-127"><xref:System.AppDomainManager> загружается в каждый <xref:System.AppDomain> при создании <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="83877-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="83877-128">Если он выбран, среда CLR уведомляет узел о том, что домен приложения был создан, установив значение параметра `pUnkAppDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="83877-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="83877-129">В реализации метода `SetAppDomainManager` узел может задать имя и тип сборки для диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83877-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83877-130">Требования</span><span class="sxs-lookup"><span data-stu-id="83877-130">Requirements</span></span>  
 <span data-ttu-id="83877-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83877-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83877-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="83877-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83877-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83877-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83877-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83877-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83877-135">См. также</span><span class="sxs-lookup"><span data-stu-id="83877-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="83877-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="83877-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
