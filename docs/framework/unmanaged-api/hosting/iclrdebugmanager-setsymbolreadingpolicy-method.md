---
title: Метод ICLRDebugManager::SetSymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2dc3d350f5c97736b3b65c814a668195aceef2b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969992"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="24964-102">Метод ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="24964-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="24964-103">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="24964-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="24964-104">Политика определяет, включаются ли сведения о файлах и номера строк в стеках вызовов.</span><span class="sxs-lookup"><span data-stu-id="24964-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24964-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24964-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24964-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="24964-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="24964-107">[in] Является членом [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="24964-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24964-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24964-108">Return Value</span></span>  
  
|<span data-ttu-id="24964-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24964-109">HRESULT</span></span>|<span data-ttu-id="24964-110">Описание</span><span class="sxs-lookup"><span data-stu-id="24964-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24964-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="24964-111">S_OK</span></span>|<span data-ttu-id="24964-112">`SetSymbolReadingPolicy` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="24964-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="24964-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24964-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24964-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="24964-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24964-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24964-115">E_FAIL</span></span>|<span data-ttu-id="24964-116">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="24964-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24964-117">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="24964-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24964-118">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="24964-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24964-119">Требования</span><span class="sxs-lookup"><span data-stu-id="24964-119">Requirements</span></span>  
 <span data-ttu-id="24964-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24964-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24964-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24964-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24964-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24964-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24964-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24964-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24964-124">См. также</span><span class="sxs-lookup"><span data-stu-id="24964-124">See also</span></span>

- [<span data-ttu-id="24964-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="24964-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
