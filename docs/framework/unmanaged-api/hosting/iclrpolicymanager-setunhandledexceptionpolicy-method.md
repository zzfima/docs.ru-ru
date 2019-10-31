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
ms.openlocfilehash: 7b6a4be94e526e7b464b336d221eff936808635a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120569"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="509d5-102">Метод ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="509d5-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="509d5-103">Задает поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="509d5-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="509d5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="509d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="509d5-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="509d5-106">окне Одно из значений [еклрунхандледексцептион](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) , указывающее, задано ли поведение средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="509d5-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="509d5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="509d5-107">Return Value</span></span>  
  
|<span data-ttu-id="509d5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="509d5-108">HRESULT</span></span>|<span data-ttu-id="509d5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="509d5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="509d5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="509d5-110">S_OK</span></span>|<span data-ttu-id="509d5-111">`SetUnhandledExceptionPolicy` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="509d5-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="509d5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="509d5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="509d5-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="509d5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="509d5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="509d5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="509d5-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="509d5-115">The call timed out.</span></span>|  
|<span data-ttu-id="509d5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="509d5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="509d5-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="509d5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="509d5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="509d5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="509d5-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="509d5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="509d5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="509d5-120">E_FAIL</span></span>|<span data-ttu-id="509d5-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="509d5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="509d5-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="509d5-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="509d5-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="509d5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="509d5-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="509d5-124">Remarks</span></span>  
 <span data-ttu-id="509d5-125">По умолчанию CLR является окончательным обработчиком для всех необработанных исключений, и его поведение по умолчанию заключается в том, чтобы разорвать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="509d5-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="509d5-126">Узел может изменить это поведение, задав для `policy` значение Ехостдетерминедполици.</span><span class="sxs-lookup"><span data-stu-id="509d5-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="509d5-127">Это значение позволяет ведущему приложению реализовать собственное поведение по умолчанию, как в предыдущих версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="509d5-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509d5-128">Требования</span><span class="sxs-lookup"><span data-stu-id="509d5-128">Requirements</span></span>  
 <span data-ttu-id="509d5-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="509d5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="509d5-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="509d5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="509d5-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="509d5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="509d5-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509d5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509d5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="509d5-133">See also</span></span>

- [<span data-ttu-id="509d5-134">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="509d5-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="509d5-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="509d5-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="509d5-136">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="509d5-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="509d5-137">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="509d5-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
