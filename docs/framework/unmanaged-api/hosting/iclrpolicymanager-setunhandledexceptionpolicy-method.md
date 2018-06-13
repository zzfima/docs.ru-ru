---
title: Метод ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6a3d5bb8a8cc5acc88373fa4952848d08ccd485
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434920"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="0d512-102">Метод ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="0d512-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="0d512-103">Определяет поведение среды common language runtime (CLR), при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="0d512-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d512-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d512-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d512-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d512-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="0d512-106">[in] Один из [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) значения, указывающие, установлен ли поведение среды CLR или узла.</span><span class="sxs-lookup"><span data-stu-id="0d512-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d512-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d512-107">Return Value</span></span>  
  
|<span data-ttu-id="0d512-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d512-108">HRESULT</span></span>|<span data-ttu-id="0d512-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0d512-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d512-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d512-110">S_OK</span></span>|<span data-ttu-id="0d512-111">`SetUnhandledExceptionPolicy` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0d512-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="0d512-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d512-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d512-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0d512-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d512-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d512-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d512-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0d512-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d512-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d512-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d512-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0d512-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d512-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d512-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d512-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0d512-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d512-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d512-120">E_FAIL</span></span>|<span data-ttu-id="0d512-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0d512-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d512-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0d512-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d512-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d512-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d512-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d512-124">Remarks</span></span>  
 <span data-ttu-id="0d512-125">По умолчанию среда CLR выполняет роль конечного обработчика для всех необработанных исключений, а его поведение по умолчанию — привести к сбою процесса.</span><span class="sxs-lookup"><span data-stu-id="0d512-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="0d512-126">Узел можно изменить это поведение, задав `policy` значение eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="0d512-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="0d512-127">Это значение позволяет ведущему приложению реализовать собственное поведение по умолчанию, как и в более ранних версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0d512-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d512-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0d512-128">Requirements</span></span>  
 <span data-ttu-id="0d512-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d512-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d512-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d512-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d512-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d512-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d512-132">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d512-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d512-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0d512-133">See Also</span></span>  
 [<span data-ttu-id="0d512-134">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="0d512-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [<span data-ttu-id="0d512-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0d512-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0d512-136">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0d512-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="0d512-137">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0d512-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
