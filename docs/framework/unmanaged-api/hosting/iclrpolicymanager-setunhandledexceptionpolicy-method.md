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
ms.openlocfilehash: 9f988084310b920907bb7f212e7d40ca0d1c91db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638545"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="b24d7-102">Метод ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="b24d7-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="b24d7-103">Задает поведение общеязыковой среды выполнения (CLR), при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="b24d7-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b24d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b24d7-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b24d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b24d7-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="b24d7-106">[in] Один из [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) значения, указывающие, установлен ли поведение среды CLR или узла.</span><span class="sxs-lookup"><span data-stu-id="b24d7-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b24d7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b24d7-107">Return Value</span></span>  
  
|<span data-ttu-id="b24d7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b24d7-108">HRESULT</span></span>|<span data-ttu-id="b24d7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b24d7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b24d7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b24d7-110">S_OK</span></span>|<span data-ttu-id="b24d7-111">`SetUnhandledExceptionPolicy` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b24d7-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="b24d7-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b24d7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b24d7-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b24d7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b24d7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b24d7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b24d7-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b24d7-115">The call timed out.</span></span>|  
|<span data-ttu-id="b24d7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b24d7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b24d7-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b24d7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b24d7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b24d7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b24d7-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b24d7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b24d7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b24d7-120">E_FAIL</span></span>|<span data-ttu-id="b24d7-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b24d7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b24d7-122">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="b24d7-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b24d7-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b24d7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b24d7-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b24d7-124">Remarks</span></span>  
 <span data-ttu-id="b24d7-125">По умолчанию среда CLR является окончательной обработчиком для все необработанные исключения, и его поведение по умолчанию — уничтожить процесс.</span><span class="sxs-lookup"><span data-stu-id="b24d7-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="b24d7-126">Управляющее приложение может изменить это поведение, задав `policy` значение eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="b24d7-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="b24d7-127">Это значение позволяет ведущему приложению реализовать собственное поведение по умолчанию, как и в более ранних версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b24d7-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b24d7-128">Требования</span><span class="sxs-lookup"><span data-stu-id="b24d7-128">Requirements</span></span>  
 <span data-ttu-id="b24d7-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b24d7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b24d7-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b24d7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b24d7-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b24d7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b24d7-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b24d7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b24d7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b24d7-133">See also</span></span>

- [<span data-ttu-id="b24d7-134">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="b24d7-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="b24d7-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b24d7-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b24d7-136">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b24d7-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="b24d7-137">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b24d7-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
