---
title: Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079660"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="715b0-102">Метод ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="715b0-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="715b0-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="715b0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="715b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="715b0-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="715b0-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="715b0-105">Return Value</span></span>  
  
|<span data-ttu-id="715b0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="715b0-106">HRESULT</span></span>|<span data-ttu-id="715b0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="715b0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="715b0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="715b0-108">S_OK</span></span>|`SetEagerSerializeGrantSets` <span data-ttu-id="715b0-109">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="715b0-109">returned successfully.</span></span>|  
|<span data-ttu-id="715b0-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="715b0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="715b0-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="715b0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="715b0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="715b0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="715b0-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="715b0-113">The call timed out.</span></span>|  
|<span data-ttu-id="715b0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="715b0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="715b0-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="715b0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="715b0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="715b0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="715b0-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="715b0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="715b0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="715b0-118">E_FAIL</span></span>|<span data-ttu-id="715b0-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="715b0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="715b0-120">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="715b0-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="715b0-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="715b0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="715b0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="715b0-122">Requirements</span></span>  
 <span data-ttu-id="715b0-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="715b0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="715b0-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="715b0-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="715b0-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="715b0-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="715b0-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="715b0-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="715b0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="715b0-127">See also</span></span>

- [<span data-ttu-id="715b0-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="715b0-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="715b0-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="715b0-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
