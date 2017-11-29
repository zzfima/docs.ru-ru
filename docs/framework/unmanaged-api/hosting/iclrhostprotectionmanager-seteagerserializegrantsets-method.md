---
title: "Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9b1e314f7af6edf3d8db00780105dff95868a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="ab7f0-102">Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="ab7f0-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="ab7f0-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab7f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab7f0-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ab7f0-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab7f0-105">Return Value</span></span>  
  
|<span data-ttu-id="ab7f0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab7f0-106">HRESULT</span></span>|<span data-ttu-id="ab7f0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ab7f0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab7f0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab7f0-108">S_OK</span></span>|<span data-ttu-id="ab7f0-109">`SetEagerSerializeGrantSets`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="ab7f0-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab7f0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab7f0-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab7f0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab7f0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab7f0-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-113">The call timed out.</span></span>|  
|<span data-ttu-id="ab7f0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab7f0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab7f0-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab7f0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab7f0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab7f0-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab7f0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab7f0-118">E_FAIL</span></span>|<span data-ttu-id="ab7f0-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab7f0-120">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab7f0-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ab7f0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab7f0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="ab7f0-122">Requirements</span></span>  
 <span data-ttu-id="ab7f0-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab7f0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab7f0-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab7f0-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab7f0-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab7f0-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab7f0-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab7f0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7f0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ab7f0-127">See Also</span></span>  
 [<span data-ttu-id="ab7f0-128">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ab7f0-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="ab7f0-129">Iclrhostprotectionmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ab7f0-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
