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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fd0cf4f47781afb397c1fdd4b42715c710982e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580763"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="cb330-102">Метод IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="cb330-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="cb330-103">Уведомляет ведущее приложение для создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cb330-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb330-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb330-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb330-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb330-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="cb330-106">[in] Числовой идентификатор выбранного <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="cb330-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="cb330-107">[in] Указатель на <xref:System.AppDomainManager> объект, реализующий узла как `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="cb330-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb330-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb330-108">Return Value</span></span>  
  
|<span data-ttu-id="cb330-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb330-109">HRESULT</span></span>|<span data-ttu-id="cb330-110">Описание</span><span class="sxs-lookup"><span data-stu-id="cb330-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb330-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb330-111">S_OK</span></span>|<span data-ttu-id="cb330-112">`SetAppDomainManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cb330-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="cb330-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb330-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb330-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cb330-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb330-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb330-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb330-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cb330-116">The call timed out.</span></span>|  
|<span data-ttu-id="cb330-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb330-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb330-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cb330-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb330-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb330-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb330-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cb330-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb330-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb330-121">E_FAIL</span></span>|<span data-ttu-id="cb330-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="cb330-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb330-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cb330-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb330-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb330-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb330-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb330-125">Remarks</span></span>  
 <span data-ttu-id="cb330-126"><xref:System.AppDomainManager> Предоставляет механизм для начальной загрузки в управляемый код, так и для управления созданием и параметры каждого основному <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="cb330-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="cb330-127"><xref:System.AppDomainManager> Загружается в каждом <xref:System.AppDomain> при, <xref:System.AppDomain> создается.</span><span class="sxs-lookup"><span data-stu-id="cb330-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="cb330-128">Если это предусмотрено, среда CLR Уведомляет основное приложение создания домена приложения, задав значение `pUnkAppDomainManager` параметра.</span><span class="sxs-lookup"><span data-stu-id="cb330-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="cb330-129">В своей реализации `SetAppDomainManager` метод, узел можно задать имя сборки и тип для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cb330-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb330-130">Требования</span><span class="sxs-lookup"><span data-stu-id="cb330-130">Requirements</span></span>  
 <span data-ttu-id="cb330-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb330-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb330-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb330-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb330-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb330-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb330-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb330-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb330-135">См. также</span><span class="sxs-lookup"><span data-stu-id="cb330-135">See also</span></span>
- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="cb330-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="cb330-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
