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
ms.openlocfilehash: 6737b953f39c1087d01f3fb864d84340a6968aba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129354"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="8a168-102">Метод ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="8a168-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="8a168-103">Задает политику чтения файлов базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="8a168-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="8a168-104">Политика определяет, включаются ли в стеки вызовов сведения о номерах строк и файлах.</span><span class="sxs-lookup"><span data-stu-id="8a168-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a168-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a168-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a168-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a168-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="8a168-107">окне Член перечисления [есимболреадингполици](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8a168-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a168-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a168-108">Return Value</span></span>  
  
|<span data-ttu-id="8a168-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a168-109">HRESULT</span></span>|<span data-ttu-id="8a168-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8a168-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a168-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a168-111">S_OK</span></span>|<span data-ttu-id="8a168-112">`SetSymbolReadingPolicy` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="8a168-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="8a168-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a168-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a168-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8a168-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a168-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a168-115">E_FAIL</span></span>|<span data-ttu-id="8a168-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a168-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a168-117">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8a168-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a168-118">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a168-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a168-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8a168-119">Requirements</span></span>  
 <span data-ttu-id="8a168-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a168-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a168-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a168-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a168-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a168-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a168-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a168-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a168-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8a168-124">See also</span></span>

- [<span data-ttu-id="8a168-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="8a168-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
