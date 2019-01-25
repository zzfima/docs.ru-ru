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
ms.openlocfilehash: 330501e67e3f19fbdb24c200deacad68de1b6c03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710297"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="d34a1-102">Метод ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="d34a1-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="d34a1-103">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="d34a1-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="d34a1-104">Политика определяет, включаются ли сведения о файлах и номера строк в стеках вызовов.</span><span class="sxs-lookup"><span data-stu-id="d34a1-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d34a1-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34a1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d34a1-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="d34a1-107">[in] Является членом [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="d34a1-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d34a1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d34a1-108">Return Value</span></span>  
  
|<span data-ttu-id="d34a1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d34a1-109">HRESULT</span></span>|<span data-ttu-id="d34a1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d34a1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d34a1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d34a1-111">S_OK</span></span>|<span data-ttu-id="d34a1-112">`SetSymbolReadingPolicy` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d34a1-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="d34a1-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d34a1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d34a1-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d34a1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d34a1-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d34a1-115">E_FAIL</span></span>|<span data-ttu-id="d34a1-116">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d34a1-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d34a1-117">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="d34a1-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d34a1-118">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d34a1-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d34a1-119">Требования</span><span class="sxs-lookup"><span data-stu-id="d34a1-119">Requirements</span></span>  
 <span data-ttu-id="d34a1-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d34a1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34a1-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d34a1-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d34a1-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d34a1-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d34a1-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34a1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34a1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d34a1-124">See also</span></span>
- [<span data-ttu-id="d34a1-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="d34a1-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
